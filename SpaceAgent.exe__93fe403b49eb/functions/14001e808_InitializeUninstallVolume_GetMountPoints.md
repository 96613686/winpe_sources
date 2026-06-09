# InitializeUninstallVolume_GetMountPoints

- ea: `0x14001e808`
- end: `0x14001ea9d`
- name: `InitializeUninstallVolume_GetMountPoints`
- size: `661`
- prototype: `__int64 __fastcall(LPCWSTR lpszRootPathName, _DWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, installer_update`

## callers

- `0x14001e464`

## callees

- `0x1400027fc`
- `0x14001e808`

## import_xrefs

- `KERNEL32!FindNextVolumeMountPointW` at `0x14001e95a`
- `KERNEL32!FindNextVolumeMountPointW` at `0x14001e95a`
- `KERNEL32!FindVolumeMountPointClose` at `0x14001e9b6`
- `KERNEL32!FindVolumeMountPointClose` at `0x14001e9b6`
- `KERNEL32!FindFirstVolumeMountPointW` at `0x14001e88d`
- `KERNEL32!FindFirstVolumeMountPointW` at `0x14001e88d`
- `KERNEL32!HeapReAlloc` at `0x14001e8f3`
- `KERNEL32!HeapReAlloc` at `0x14001e919`
- `KERNEL32!HeapReAlloc` at `0x14001e9e8`
- `KERNEL32!HeapReAlloc` at `0x14001e8f3`
- `KERNEL32!HeapReAlloc` at `0x14001e919`
- `KERNEL32!HeapReAlloc` at `0x14001e9e8`
- `KERNEL32!HeapAlloc` at `0x14001e845`
- `KERNEL32!HeapAlloc` at `0x14001e86e`
- `KERNEL32!HeapAlloc` at `0x14001e939`
- `KERNEL32!HeapAlloc` at `0x14001e845`
- `KERNEL32!HeapAlloc` at `0x14001e86e`
- `KERNEL32!HeapAlloc` at `0x14001e939`
- `KERNEL32!HeapFree` at `0x14001e988`
- `KERNEL32!HeapFree` at `0x14001e9ff`
- `KERNEL32!HeapFree` at `0x14001ea3e`
- `KERNEL32!HeapFree` at `0x14001ea55`
- `KERNEL32!HeapFree` at `0x14001e988`
- `KERNEL32!HeapFree` at `0x14001e9ff`
- `KERNEL32!HeapFree` at `0x14001ea3e`
- `KERNEL32!HeapFree` at `0x14001ea55`
- `KERNEL32!GetProcessHeap` at `0x14001e82a`
- `KERNEL32!GetProcessHeap` at `0x14001e82a`
- `KERNEL32!SetLastError` at `0x14001e858`
- `KERNEL32!SetLastError` at `0x14001e999`
- `KERNEL32!SetLastError` at `0x14001ea80`
- `KERNEL32!SetLastError` at `0x14001e858`
- `KERNEL32!SetLastError` at `0x14001e999`
- `KERNEL32!SetLastError` at `0x14001ea80`
- `KERNEL32!GetLastError` at `0x14001e89c`
- `KERNEL32!GetLastError` at `0x14001e96a`
- `KERNEL32!GetLastError` at `0x14001e9a4`
- `KERNEL32!GetLastError` at `0x14001e9c6`
- `KERNEL32!GetLastError` at `0x14001ea66`
- `KERNEL32!GetLastError` at `0x14001e89c`
- `KERNEL32!GetLastError` at `0x14001e96a`
- `KERNEL32!GetLastError` at `0x14001e9a4`
- `KERNEL32!GetLastError` at `0x14001e9c6`
- `KERNEL32!GetLastError` at `0x14001ea66`

## pseudocode

```c
__int64 __fastcall InitializeUninstallVolume_GetMountPoints(LPCWSTR lpszRootPathName, _DWORD *a2, _QWORD *a3)
{
  _DWORD *v4; // r15
  __int64 v6; // rsi
  HANDLE ProcessHeap; // rbp
  __int64 FirstVolumeMountPointW; // r12
  _QWORD *v9; // rdi
  DWORD v10; // ecx
  unsigned int NextVolumeMountPointW; // ebx
  WCHAR *v12; // rax
  __int64 v13; // rbx
  int v14; // eax
  LPVOID v15; // rax
  _QWORD *v16; // rax
  _QWORD *v17; // rbx
  WCHAR *v18; // rax
  DWORD v19; // ecx
  DWORD LastError; // r14d
  BOOL VolumeMountPointClose; // eax
  void *v22; // r8
  _QWORD *v23; // rax
  DWORD v24; // eax
  DWORD v25; // ecx
  unsigned __int64 v28; // [rsp+78h] [rbp+20h] BYREF

  v4 = a2;
  LODWORD(v6) = 0;
  ProcessHeap = GetProcessHeap();
  FirstVolumeMountPointW = -1;
  v9 = HeapAlloc(ProcessHeap, 0, 8u);
  if ( v9 )
  {
    v12 = (WCHAR *)HeapAlloc(ProcessHeap, 0, 0x10000u);
    *v9 = v12;
    if ( v12 )
    {
      LODWORD(v6) = 1;
      FirstVolumeMountPointW = (__int64)FindFirstVolumeMountPointW(lpszRootPathName, v12, 0x8000u);
      if ( FirstVolumeMountPointW == -1 )
      {
        if ( GetLastError() != 18 )
        {
          NextVolumeMountPointW = 0;
          goto LABEL_19;
        }
      }
      else
      {
        do
        {
          v28 = 0;
          v13 = (unsigned int)(v6 - 1);
          v14 = StringCchLengthW((const unsigned __int16 *)v9[v13], 0x8000u, &v28);
          v10 = v14;
          if ( v14 < 0 )
          {
            NextVolumeMountPointW = 0;
            if ( (v14 & 0x1FFF0000) == 0x70000 )
              v10 = (unsigned __int16)v14;
            goto LABEL_4;
          }
          v15 = HeapReAlloc(ProcessHeap, 0, (LPVOID)v9[v13], 2 * v28 + 2);
          if ( !v15
            || (v9[v13] = v15, v16 = HeapReAlloc(ProcessHeap, 0, v9, 8LL * (unsigned int)v6 + 8), (v17 = v16) == 0)
            || (v9 = v16, v18 = (WCHAR *)HeapAlloc(ProcessHeap, 0, 0x10000u), (v17[(unsigned int)v6] = v18) == 0) )
          {
            v10 = 8;
            goto LABEL_3;
          }
          LODWORD(v6) = v6 + 1;
          NextVolumeMountPointW = FindNextVolumeMountPointW((HANDLE)FirstVolumeMountPointW, v18, 0x8000u);
        }
        while ( NextVolumeMountPointW );
        if ( GetLastError() != 18 )
          goto LABEL_19;
      }
      v6 = (unsigned int)(v6 - 1);
      NextVolumeMountPointW = HeapFree(ProcessHeap, 0, (LPVOID)v9[v6]);
      if ( NextVolumeMountPointW )
      {
        v22 = v9;
        if ( (_DWORD)v6 )
        {
          v23 = HeapReAlloc(ProcessHeap, 0, v9, 8 * v6);
          if ( v23 )
          {
            v9 = v23;
            goto LABEL_18;
          }
          NextVolumeMountPointW = 0;
          v19 = 8;
LABEL_17:
          SetLastError(v19);
LABEL_18:
          v4 = a2;
          goto LABEL_19;
        }
        v9 = 0;
        NextVolumeMountPointW = HeapFree(ProcessHeap, 0, v22);
        if ( NextVolumeMountPointW )
          goto LABEL_18;
      }
      v19 = 6;
      goto LABEL_17;
    }
  }
  v10 = 8;
LABEL_3:
  NextVolumeMountPointW = 0;
LABEL_4:
  SetLastError(v10);
LABEL_19:
  LastError = GetLastError();
  if ( FirstVolumeMountPointW == -1 )
    goto LABEL_22;
  VolumeMountPointClose = FindVolumeMountPointClose((HANDLE)FirstVolumeMountPointW);
  if ( NextVolumeMountPointW )
  {
    NextVolumeMountPointW = VolumeMountPointClose;
    LastError = GetLastError();
LABEL_22:
    if ( NextVolumeMountPointW )
      goto LABEL_38;
  }
  while ( (_DWORD)v6 )
  {
    v6 = (unsigned int)(v6 - 1);
    HeapFree(ProcessHeap, 0, (LPVOID)v9[v6]);
  }
  if ( v9 )
    HeapFree(ProcessHeap, 0, v9);
  v9 = 0;
  LODWORD(v6) = 0;
LABEL_38:
  *v4 = v6;
  *a3 = v9;
  v24 = GetLastError();
  if ( v24 == 3 )
    NextVolumeMountPointW = 1;
  v25 = 0;
  if ( v24 != 3 )
    v25 = LastError;
  SetLastError(v25);
  return NextVolumeMountPointW;
}

```

## disassembly

```asm
0x14001e808  mov     [rsp+arg_0], rbx
0x14001e80d  mov     [rsp+arg_8], rdx
0x14001e812  push    rbp
0x14001e813  push    rsi
0x14001e814  push    rdi
0x14001e815  push    r12
0x14001e817  push    r13
0x14001e819  push    r14
0x14001e81b  push    r15
0x14001e81d  sub     rsp, 20h
0x14001e821  mov     r13, r8
0x14001e824  mov     r15, rdx
0x14001e827  mov     rbx, rcx
0x14001e82a  call    cs:__imp_GetProcessHeap
0x14001e830  xor     esi, esi
0x14001e832  xor     edx, edx; dwFlags
0x14001e834  mov     rcx, rax; hHeap
0x14001e837  mov     rbp, rax
0x14001e83a  or      r12, 0FFFFFFFFFFFFFFFFh
0x14001e83e  lea     r14d, [rsi+8]
0x14001e842  mov     r8d, r14d; dwBytes
0x14001e845  call    cs:__imp_HeapAlloc
0x14001e84b  mov     rdi, rax
0x14001e84e  test    rax, rax
0x14001e851  jnz     short loc_14001E863
0x14001e853  mov     ecx, r14d; dwErrCode
0x14001e856  xor     ebx, ebx
0x14001e858  call    cs:__imp_SetLastError
0x14001e85e  jmp     loc_14001E9A4
0x14001e863  xor     edx, edx; dwFlags
0x14001e865  mov     r8d, 10000h; dwBytes
0x14001e86b  mov     rcx, rbp; hHeap
0x14001e86e  call    cs:__imp_HeapAlloc
0x14001e874  mov     [rdi], rax
0x14001e877  test    rax, rax
0x14001e87a  jz      short loc_14001E853
0x14001e87c  mov     r8d, 8000h; cchBufferLength
0x14001e882  mov     rdx, rax; lpszVolumeMountPoint
0x14001e885  mov     rcx, rbx; lpszRootPathName
0x14001e888  mov     esi, 1
0x14001e88d  call    cs:__imp_FindFirstVolumeMountPointW
0x14001e893  mov     r12, rax
0x14001e896  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14001e89a  jnz     short loc_14001E8B2
0x14001e89c  call    cs:__imp_GetLastError
0x14001e8a2  cmp     eax, 12h
0x14001e8a5  jz      loc_14001E975
0x14001e8ab  xor     ebx, ebx
0x14001e8ad  jmp     loc_14001E9A4
0x14001e8b2  lea     eax, [rsi-1]
0x14001e8b5  mov     [rsp+58h+arg_18], 0
0x14001e8be  mov     rcx, [rdi+rax*8]; unsigned __int16 *
0x14001e8c2  lea     r8, [rsp+58h+arg_18]; unsigned __int64 *
0x14001e8c7  mov     edx, 8000h; unsigned __int64
0x14001e8cc  mov     ebx, eax
0x14001e8ce  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x14001e8d3  mov     ecx, eax
0x14001e8d5  test    eax, eax
0x14001e8d7  js      loc_14001EA19
0x14001e8dd  mov     r9, [rsp+58h+arg_18]
0x14001e8e2  xor     edx, edx; dwFlags
0x14001e8e4  mov     r8, [rdi+rbx*8]; lpMem
0x14001e8e8  mov     rcx, rbp; hHeap
0x14001e8eb  lea     r9, ds:2[r9*2]; dwBytes
0x14001e8f3  call    cs:__imp_HeapReAlloc
0x14001e8f9  test    rax, rax
0x14001e8fc  jz      loc_14001EA0F
0x14001e902  mov     r14d, esi
0x14001e905  mov     r8, rdi; lpMem
0x14001e908  xor     edx, edx; dwFlags
0x14001e90a  mov     [rdi+rbx*8], rax
0x14001e90e  mov     rcx, rbp; hHeap
0x14001e911  lea     r9, ds:8[r14*8]; dwBytes
0x14001e919  call    cs:__imp_HeapReAlloc
0x14001e91f  mov     rbx, rax
0x14001e922  test    rax, rax
0x14001e925  jz      loc_14001EA0F
0x14001e92b  xor     edx, edx; dwFlags
0x14001e92d  mov     r8d, 10000h; dwBytes
0x14001e933  mov     rcx, rbp; hHeap
0x14001e936  mov     rdi, rax
0x14001e939  call    cs:__imp_HeapAlloc
0x14001e93f  mov     [rbx+r14*8], rax
0x14001e943  test    rax, rax
0x14001e946  jz      loc_14001EA0F
0x14001e94c  mov     r8d, 8000h; cchBufferLength
0x14001e952  mov     rdx, rax; lpszVolumeMountPoint
0x14001e955  mov     rcx, r12; hFindVolumeMountPoint
0x14001e958  inc     esi
0x14001e95a  call    cs:__imp_FindNextVolumeMountPointW
0x14001e960  mov     ebx, eax
0x14001e962  test    eax, eax
0x14001e964  jnz     loc_14001E8B2
0x14001e96a  call    cs:__imp_GetLastError
0x14001e970  cmp     eax, 12h
0x14001e973  jnz     short loc_14001E9A4
0x14001e975  dec     esi
0x14001e977  xor     edx, edx; dwFlags
0x14001e979  mov     rcx, rbp; hHeap
0x14001e97c  lea     r15, ds:0[rsi*8]
0x14001e984  mov     r8, [r15+rdi]; lpMem
0x14001e988  call    cs:__imp_HeapFree
0x14001e98e  mov     ebx, eax
0x14001e990  test    eax, eax
0x14001e992  jnz     short loc_14001E9D9
0x14001e994  mov     ecx, 6; dwErrCode
0x14001e999  call    cs:__imp_SetLastError
0x14001e99f  mov     r15, [rsp+58h+arg_8]
0x14001e9a4  call    cs:__imp_GetLastError
0x14001e9aa  mov     r14d, eax
0x14001e9ad  cmp     r12, 0FFFFFFFFFFFFFFFFh
0x14001e9b1  jz      short loc_14001E9CF
0x14001e9b3  mov     rcx, r12; hFindVolumeMountPoint
0x14001e9b6  call    cs:__imp_FindVolumeMountPointClose
0x14001e9bc  test    ebx, ebx
0x14001e9be  jz      loc_14001EA44
0x14001e9c4  mov     ebx, eax
0x14001e9c6  call    cs:__imp_GetLastError
0x14001e9cc  mov     r14d, eax
0x14001e9cf  test    ebx, ebx
0x14001e9d1  jnz     loc_14001EA5F
0x14001e9d7  jmp     short loc_14001EA44
0x14001e9d9  xor     edx, edx; dwFlags
0x14001e9db  mov     r8, rdi; lpMem
0x14001e9de  mov     rcx, rbp; hHeap
0x14001e9e1  test    esi, esi
0x14001e9e3  jz      short loc_14001E9FF
0x14001e9e5  mov     r9, r15; dwBytes
0x14001e9e8  call    cs:__imp_HeapReAlloc
0x14001e9ee  test    rax, rax
0x14001e9f1  jnz     short loc_14001E9FA
0x14001e9f3  xor     ebx, ebx
0x14001e9f5  lea     ecx, [rax+8]
0x14001e9f8  jmp     short loc_14001E999
0x14001e9fa  mov     rdi, rax
0x14001e9fd  jmp     short loc_14001E99F
0x14001e9ff  call    cs:__imp_HeapFree
0x14001ea05  xor     edi, edi
0x14001ea07  mov     ebx, eax
0x14001ea09  test    eax, eax
0x14001ea0b  jnz     short loc_14001E99F
0x14001ea0d  jmp     short loc_14001E994
0x14001ea0f  mov     ecx, 8
0x14001ea14  jmp     loc_14001E856
0x14001ea19  xor     ebx, ebx
0x14001ea1b  and     eax, 1FFF0000h
0x14001ea20  cmp     eax, 70000h
0x14001ea25  jnz     loc_14001E858
0x14001ea2b  movzx   ecx, cx
0x14001ea2e  jmp     loc_14001E858
0x14001ea33  dec     esi
0x14001ea35  xor     edx, edx; dwFlags
0x14001ea37  mov     rcx, rbp; hHeap
0x14001ea3a  mov     r8, [rdi+rsi*8]; lpMem
0x14001ea3e  call    cs:__imp_HeapFree
0x14001ea44  test    esi, esi
0x14001ea46  jnz     short loc_14001EA33
0x14001ea48  test    rdi, rdi
0x14001ea4b  jz      short loc_14001EA5B
0x14001ea4d  mov     r8, rdi; lpMem
0x14001ea50  xor     edx, edx; dwFlags
0x14001ea52  mov     rcx, rbp; hHeap
0x14001ea55  call    cs:__imp_HeapFree
0x14001ea5b  xor     edi, edi
0x14001ea5d  xor     esi, esi
0x14001ea5f  mov     [r15], esi
0x14001ea62  mov     [r13+0], rdi
0x14001ea66  call    cs:__imp_GetLastError
0x14001ea6c  cmp     eax, 3
0x14001ea6f  mov     ecx, 1
0x14001ea74  cmovz   ebx, ecx
0x14001ea77  xor     ecx, ecx
0x14001ea79  cmp     eax, 3
0x14001ea7c  cmovnz  ecx, r14d; dwErrCode
0x14001ea80  call    cs:__imp_SetLastError
0x14001ea86  mov     eax, ebx
0x14001ea88  mov     rbx, [rsp+58h+arg_0]
0x14001ea8d  add     rsp, 20h
0x14001ea91  pop     r15
0x14001ea93  pop     r14
0x14001ea95  pop     r13
0x14001ea97  pop     r12
0x14001ea99  pop     rdi
0x14001ea9a  pop     rsi
0x14001ea9b  pop     rbp
0x14001ea9c  retn
```
