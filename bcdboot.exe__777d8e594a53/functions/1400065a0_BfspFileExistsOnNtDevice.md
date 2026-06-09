# BfspFileExistsOnNtDevice

- ea: `0x1400065a0`
- end: `0x14000683e`
- name: `BfspFileExistsOnNtDevice`
- size: `670`
- prototype: `__int64 __fastcall(__int64, const wchar_t *, _DWORD *)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, reparse_path`

## callers

- `0x140008694`
- `0x140009170`

## callees

- `0x1400065a0`
- `0x140006844`
- `0x140007780`
- `0x14000e628`
- `0x140026650`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x140006614`
- `msvcrt!_wcsicmp` at `0x140006614`
- `msvcrt!wcscpy_s` at `0x140006701`
- `msvcrt!wcscpy_s` at `0x140006701`
- `msvcrt!swprintf_s` at `0x14000678e`
- `msvcrt!swprintf_s` at `0x14000678e`
- `KERNEL32!HeapFree` at `0x1400067d2`
- `KERNEL32!HeapFree` at `0x1400067f9`
- `KERNEL32!HeapFree` at `0x1400067d2`
- `KERNEL32!HeapFree` at `0x1400067f9`
- `KERNEL32!HeapAlloc` at `0x1400066d0`
- `KERNEL32!HeapAlloc` at `0x140006755`
- `KERNEL32!HeapAlloc` at `0x1400066d0`
- `KERNEL32!HeapAlloc` at `0x140006755`
- `KERNEL32!GetProcessHeap` at `0x1400066bf`
- `KERNEL32!GetProcessHeap` at `0x140006744`
- `KERNEL32!GetProcessHeap` at `0x1400067c4`
- `KERNEL32!GetProcessHeap` at `0x1400067eb`
- `KERNEL32!GetProcessHeap` at `0x1400066bf`
- `KERNEL32!GetProcessHeap` at `0x140006744`
- `KERNEL32!GetProcessHeap` at `0x1400067c4`
- `KERNEL32!GetProcessHeap` at `0x1400067eb`
- `KERNEL32!QueryDosDeviceW` at `0x1400065ff`
- `KERNEL32!QueryDosDeviceW` at `0x1400065ff`
- `KERNEL32!GetFileAttributesW` at `0x1400067b2`
- `KERNEL32!GetFileAttributesW` at `0x1400067b2`
- `KERNEL32!DeleteVolumeMountPointW` at `0x1400067e0`
- `KERNEL32!DeleteVolumeMountPointW` at `0x1400067e0`

## string_xrefs

- `0x14000665c`: `Attempting to mount device %ws with volume name %ws`
- `0x14000668c`: `Failed to mount device %ws`
- `0x140006763`: `Failed to allocate space for full path`
- `0x140006799`: `Failed to create full file path`

## pseudocode

```c
__int64 __fastcall BfspFileExistsOnNtDevice(__int64 a1, const wchar_t *a2, _DWORD *a3)
{
  int v6; // r15d
  int VolumeNameForDeviceName; // esi
  const WCHAR *v8; // rbx
  WCHAR *v9; // rdi
  __int64 v10; // rbx
  HANDLE ProcessHeap; // rax
  wchar_t *v12; // rax
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // rax
  size_t v16; // r14
  HANDLE v17; // rax
  wchar_t *v18; // rax
  WCHAR *v19; // rbx
  HANDLE v20; // rax
  HANDLE v21; // rax
  LPCWSTR lpszVolumeName; // [rsp+38h] [rbp-81h] BYREF
  WCHAR DeviceName[8]; // [rsp+40h] [rbp-79h] BYREF
  WCHAR TargetPath[64]; // [rsp+50h] [rbp-69h] BYREF

  lpszVolumeName = 0;
  wcscpy(DeviceName, L"C:");
  v6 = 1;
  while ( !QueryDosDeviceW(DeviceName, TargetPath, 0x40u) || _wcsicmp(a2, TargetPath) )
  {
    if ( ++DeviceName[0] > 0x5Au )
      goto LABEL_5;
  }
  v10 = -1;
  do
    ++v10;
  while ( DeviceName[v10] );
  ProcessHeap = GetProcessHeap();
  v12 = (wchar_t *)HeapAlloc(ProcessHeap, 8u, 2 * v10 + 2);
  v9 = v12;
  if ( v12 )
  {
    v6 = 0;
    v13 = -1;
    do
      ++v13;
    while ( DeviceName[v13] );
    wcscpy_s(v12, v13 + 1, DeviceName);
    VolumeNameForDeviceName = 0;
    goto LABEL_16;
  }
LABEL_5:
  VolumeNameForDeviceName = BfspFindVolumeNameForDeviceName(a2, &lpszVolumeName);
  if ( VolumeNameForDeviceName < 0 || (v8 = lpszVolumeName) == 0 )
  {
    BfspLogMessage(4, L"Failed to find volume name for device %ws", a2);
    return (unsigned int)VolumeNameForDeviceName;
  }
  BfspLogMessage(2, L"Attempting to mount device %ws with volume name %ws", a2, lpszVolumeName);
  VolumeNameForDeviceName = BfspMountVolume(v8);
  if ( VolumeNameForDeviceName < 0 )
  {
    BfspLogMessage(4, L"Failed to mount device %ws", a2);
    v9 = 0;
    goto LABEL_29;
  }
  v9 = 0;
LABEL_16:
  if ( v9 )
  {
    v14 = -1;
    v15 = -1;
    do
      ++v15;
    while ( v9[v15] );
    do
      ++v14;
    while ( *(_WORD *)(a1 + 2 * v14) );
    v16 = v15 + v14 + 1;
    v17 = GetProcessHeap();
    v18 = (wchar_t *)HeapAlloc(v17, 8u, 2 * v16);
    v19 = v18;
    if ( v18 )
    {
      if ( swprintf_s(v18, v16, L"%ws%ws", v9, a1) == -1 )
      {
        BfspLogMessage(4, L"Failed to create full file path");
        VolumeNameForDeviceName = -1073741823;
      }
      else
      {
        *a3 = GetFileAttributesW(v19) != -1;
      }
      v20 = GetProcessHeap();
      HeapFree(v20, 0, v19);
    }
    else
    {
      BfspLogMessage(4, L"Failed to allocate space for full path");
      VolumeNameForDeviceName = -1073741801;
    }
  }
  else
  {
    VolumeNameForDeviceName = -1073741810;
  }
  if ( v6 )
    DeleteVolumeMountPointW(v9);
LABEL_29:
  if ( v9 )
  {
    v21 = GetProcessHeap();
    HeapFree(v21, 0, v9);
  }
  return (unsigned int)VolumeNameForDeviceName;
}

```

## disassembly

```asm
0x1400065a0  mov     [rsp-8+arg_18], rbx
0x1400065a5  push    rbp
0x1400065a6  push    rsi
0x1400065a7  push    rdi
0x1400065a8  push    r12
0x1400065aa  push    r13
0x1400065ac  push    r14
0x1400065ae  push    r15
0x1400065b0  lea     rbp, [rsp-27h]
0x1400065b5  sub     rsp, 0E0h
0x1400065bc  mov     rax, cs:__security_cookie
0x1400065c3  xor     rax, rsp
0x1400065c6  mov     [rbp+57h+var_40], rax
0x1400065ca  xor     ebx, ebx
0x1400065cc  mov     [rbp+57h+var_CE], 3Ah ; ':'
0x1400065d3  mov     r13, r8
0x1400065d6  mov     [rsp+110h+lpMem], rbx
0x1400065db  mov     r14, rdx
0x1400065de  mov     [rsp+110h+lpszVolumeName], rbx
0x1400065e3  mov     r12, rcx
0x1400065e6  lea     eax, [rbx+43h]
0x1400065e9  mov     [rbp+57h+DeviceName], ax
0x1400065ed  lea     r15d, [rbx+1]
0x1400065f1  mov     r8d, 40h ; '@'; ucchMax
0x1400065f7  lea     rdx, [rbp+57h+TargetPath]; lpTargetPath
0x1400065fb  lea     rcx, [rbp+57h+DeviceName]; lpDeviceName
0x1400065ff  call    cs:__imp_QueryDosDeviceW
0x140006605  or      rsi, 0FFFFFFFFFFFFFFFFh
0x140006609  test    eax, eax
0x14000660b  jz      short loc_140006622
0x14000660d  lea     rdx, [rbp+57h+TargetPath]; String2
0x140006611  mov     rcx, r14; String1
0x140006614  call    cs:__imp__wcsicmp
0x14000661a  test    eax, eax
0x14000661c  jz      loc_1400066A5
0x140006622  movzx   eax, [rbp+57h+DeviceName]
0x140006626  add     ax, r15w
0x14000662a  mov     [rbp+57h+DeviceName], ax
0x14000662e  cmp     ax, 5Ah ; 'Z'
0x140006632  jbe     short loc_1400065F1
0x140006634  lea     rdx, [rsp+110h+lpszVolumeName]
0x140006639  mov     rcx, r14
0x14000663c  call    BfspFindVolumeNameForDeviceName
0x140006641  mov     esi, eax
0x140006643  test    eax, eax
0x140006645  js      loc_140006801
0x14000664b  mov     rbx, [rsp+110h+lpszVolumeName]
0x140006650  test    rbx, rbx
0x140006653  jz      loc_140006801
0x140006659  mov     r9, rbx
0x14000665c  lea     rdx, aAttemptingToMo; "Attempting to mount device %ws with vol"...
0x140006663  mov     r8, r14
0x140006666  mov     ecx, 2
0x14000666b  call    BfspLogMessage
0x140006670  lea     rdx, [rsp+110h+lpMem]
0x140006675  mov     rcx, rbx; lpszVolumeName
0x140006678  call    BfspMountVolume
0x14000667d  xor     ebx, ebx
0x14000667f  mov     esi, eax
0x140006681  test    eax, eax
0x140006683  jns     loc_14000670B
0x140006689  mov     r8, r14
0x14000668c  lea     rdx, aFailedToMountD; "Failed to mount device %ws"
0x140006693  lea     ecx, [rbx+4]
0x140006696  call    BfspLogMessage
0x14000669b  mov     rdi, [rsp+110h+lpMem]
0x1400066a0  jmp     loc_1400067E6
0x1400066a5  lea     rax, [rbp+57h+DeviceName]
0x1400066a9  mov     rbx, rsi
0x1400066ac  xor     ecx, ecx
0x1400066ae  inc     rbx
0x1400066b1  cmp     [rax+rbx*2], cx
0x1400066b5  jnz     short loc_1400066AE
0x1400066b7  lea     rbx, ds:2[rbx*2]
0x1400066bf  call    cs:__imp_GetProcessHeap
0x1400066c5  mov     r8, rbx; dwBytes
0x1400066c8  mov     edx, 8; dwFlags
0x1400066cd  mov     rcx, rax; hHeap
0x1400066d0  call    cs:__imp_HeapAlloc
0x1400066d6  xor     ebx, ebx
0x1400066d8  mov     rdi, rax
0x1400066db  test    rax, rax
0x1400066de  jz      loc_140006634
0x1400066e4  mov     r15d, ebx
0x1400066e7  lea     rax, [rbp+57h+DeviceName]
0x1400066eb  mov     rdx, rsi
0x1400066ee  inc     rdx
0x1400066f1  cmp     [rax+rdx*2], bx
0x1400066f5  jnz     short loc_1400066EE
0x1400066f7  inc     rdx; SizeInWords
0x1400066fa  lea     r8, [rbp+57h+DeviceName]; Source
0x1400066fe  mov     rcx, rdi; Destination
0x140006701  call    cs:__imp_wcscpy_s
0x140006707  mov     esi, ebx
0x140006709  jmp     short loc_140006710
0x14000670b  mov     rdi, [rsp+110h+lpMem]
0x140006710  test    rdi, rdi
0x140006713  jnz     short loc_14000671F
0x140006715  mov     esi, 0C000000Eh
0x14000671a  jmp     loc_1400067D8
0x14000671f  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140006723  mov     rax, rcx
0x140006726  inc     rax
0x140006729  cmp     [rdi+rax*2], bx
0x14000672d  jnz     short loc_140006726
0x14000672f  inc     rcx
0x140006732  cmp     [r12+rcx*2], bx
0x140006737  jnz     short loc_14000672F
0x140006739  lea     r14, [rcx+1]
0x14000673d  add     r14, rax
0x140006740  lea     rbx, [r14+r14]
0x140006744  call    cs:__imp_GetProcessHeap
0x14000674a  mov     r8, rbx; dwBytes
0x14000674d  mov     edx, 8; dwFlags
0x140006752  mov     rcx, rax; hHeap
0x140006755  call    cs:__imp_HeapAlloc
0x14000675b  mov     rbx, rax
0x14000675e  test    rax, rax
0x140006761  jnz     short loc_140006779
0x140006763  lea     rdx, aFailedToAlloca_2; "Failed to allocate space for full path"
0x14000676a  lea     ecx, [rax+4]
0x14000676d  call    BfspLogMessage
0x140006772  mov     esi, 0C0000017h
0x140006777  jmp     short loc_1400067D8
0x140006779  mov     r9, rdi
0x14000677c  mov     [rsp+110h+var_F0], r12
0x140006781  lea     r8, aWsWs; "%ws%ws"
0x140006788  mov     rdx, r14; BufferCount
0x14000678b  mov     rcx, rbx; Buffer
0x14000678e  call    cs:__imp_swprintf_s
0x140006794  cmp     eax, 0FFFFFFFFh
0x140006797  jnz     short loc_1400067AF
0x140006799  lea     rdx, aFailedToCreate_8; "Failed to create full file path"
0x1400067a0  lea     ecx, [rax+5]
0x1400067a3  call    BfspLogMessage
0x1400067a8  mov     esi, 0C0000001h
0x1400067ad  jmp     short loc_1400067C4
0x1400067af  mov     rcx, rbx; lpFileName
0x1400067b2  call    cs:__imp_GetFileAttributesW
0x1400067b8  xor     ecx, ecx
0x1400067ba  cmp     eax, 0FFFFFFFFh
0x1400067bd  setnz   cl
0x1400067c0  mov     [r13+0], ecx
0x1400067c4  call    cs:__imp_GetProcessHeap
0x1400067ca  mov     r8, rbx; lpMem
0x1400067cd  xor     edx, edx; dwFlags
0x1400067cf  mov     rcx, rax; hHeap
0x1400067d2  call    cs:__imp_HeapFree
0x1400067d8  test    r15d, r15d
0x1400067db  jz      short loc_1400067E6
0x1400067dd  mov     rcx, rdi; lpszVolumeMountPoint
0x1400067e0  call    cs:__imp_DeleteVolumeMountPointW
0x1400067e6  test    rdi, rdi
0x1400067e9  jz      short loc_140006815
0x1400067eb  call    cs:__imp_GetProcessHeap
0x1400067f1  mov     r8, rdi; lpMem
0x1400067f4  xor     edx, edx; dwFlags
0x1400067f6  mov     rcx, rax; hHeap
0x1400067f9  call    cs:__imp_HeapFree
0x1400067ff  jmp     short loc_140006815
0x140006801  mov     r8, r14
0x140006804  lea     rdx, aFailedToFindVo; "Failed to find volume name for device %"...
0x14000680b  mov     ecx, 4
0x140006810  call    BfspLogMessage
0x140006815  mov     eax, esi
0x140006817  mov     rcx, [rbp+57h+var_40]
0x14000681b  xor     rcx, rsp; StackCookie
0x14000681e  call    __security_check_cookie
0x140006823  mov     rbx, [rsp+110h+arg_18]
0x14000682b  add     rsp, 0E0h
0x140006832  pop     r15
0x140006834  pop     r14
0x140006836  pop     r13
0x140006838  pop     r12
0x14000683a  pop     rdi
0x14000683b  pop     rsi
0x14000683c  pop     rbp
0x14000683d  retn
```
