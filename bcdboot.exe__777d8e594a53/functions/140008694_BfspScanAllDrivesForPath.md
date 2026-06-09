# BfspScanAllDrivesForPath

- ea: `0x140008694`
- end: `0x1400087a0`
- name: `BfspScanAllDrivesForPath`
- size: `268`
- prototype: `__int64 __fastcall(__int64, _DWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140009170`

## callees

- `0x1400065a0`
- `0x140008694`
- `0x1400265fa`
- `0x140026650`

## import_xrefs

- `KERNEL32!QueryDosDeviceW` at `0x140008727`
- `KERNEL32!QueryDosDeviceW` at `0x140008727`
- `KERNEL32!FindFirstVolumeW` at `0x1400086e6`
- `KERNEL32!FindFirstVolumeW` at `0x1400086e6`
- `KERNEL32!FindVolumeClose` at `0x140008770`
- `KERNEL32!FindVolumeClose` at `0x140008770`
- `KERNEL32!FindNextVolumeW` at `0x140008763`
- `KERNEL32!FindNextVolumeW` at `0x140008763`

## pseudocode

```c
__int64 __fastcall BfspScanAllDrivesForPath(__int64 a1, _DWORD *a2)
{
  HANDLE FirstVolumeW; // rdi
  int v5; // ebx
  __int64 v6; // rbx
  __int16 v8; // [rsp+1Eh] [rbp-44Ah]
  WCHAR szVolumeName; // [rsp+20h] [rbp-448h] BYREF
  _BYTE v10[6]; // [rsp+22h] [rbp-446h] BYREF
  WCHAR DeviceName[260]; // [rsp+28h] [rbp-440h] BYREF
  WCHAR TargetPath[264]; // [rsp+230h] [rbp-238h] BYREF

  szVolumeName = 0;
  memset_0(v10, 0, 0x206u);
  FirstVolumeW = FindFirstVolumeW(&szVolumeName, 0x104u);
  if ( FirstVolumeW )
  {
    do
    {
      v6 = -1;
      do
        ++v6;
      while ( *(_WORD *)&v10[2 * v6 - 2] );
      *(&v8 + v6) = 0;
      QueryDosDeviceW(DeviceName, TargetPath, 0x104u);
      *(&v8 + v6) = 92;
      v5 = BfspFileExistsOnNtDevice(a1, TargetPath, a2);
    }
    while ( v5 >= 0 && *a2 != 1 && FindNextVolumeW(FirstVolumeW, &szVolumeName, 0x104u) );
    FindVolumeClose(FirstVolumeW);
  }
  else
  {
    return (unsigned int)-1073741823;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140008694  mov     [rsp+arg_10], rbx
0x140008699  mov     [rsp+arg_18], rbp
0x14000869e  push    rsi
0x14000869f  push    rdi
0x1400086a0  push    r14
0x1400086a2  sub     rsp, 450h
0x1400086a9  mov     rax, cs:__security_cookie
0x1400086b0  xor     rax, rsp
0x1400086b3  mov     [rsp+468h+var_28], rax
0x1400086bb  mov     rsi, rdx
0x1400086be  mov     rbp, rcx
0x1400086c1  xor     r14d, r14d
0x1400086c4  lea     rcx, [rsp+468h+var_446]; void *
0x1400086c9  xor     edx, edx; Val
0x1400086cb  mov     [rsp+468h+szVolumeName], r14w
0x1400086d1  mov     r8d, 206h; Size
0x1400086d7  call    memset_0
0x1400086dc  mov     edx, 104h; cchBufferLength
0x1400086e1  lea     rcx, [rsp+468h+szVolumeName]; lpszVolumeName
0x1400086e6  call    cs:__imp_FindFirstVolumeW
0x1400086ec  mov     rdi, rax
0x1400086ef  test    rax, rax
0x1400086f2  jnz     short loc_1400086FB
0x1400086f4  mov     ebx, 0C0000001h
0x1400086f9  jmp     short loc_140008776
0x1400086fb  lea     rax, [rsp+468h+szVolumeName]
0x140008700  or      rbx, 0FFFFFFFFFFFFFFFFh
0x140008704  inc     rbx
0x140008707  cmp     [rax+rbx*2], r14w
0x14000870c  jnz     short loc_140008704
0x14000870e  mov     r8d, 104h; ucchMax
0x140008714  mov     [rsp+rbx*2+468h+var_44A], r14w
0x14000871a  lea     rdx, [rsp+468h+TargetPath]; lpTargetPath
0x140008722  lea     rcx, [rsp+468h+DeviceName]; lpDeviceName
0x140008727  call    cs:__imp_QueryDosDeviceW
0x14000872d  mov     eax, 5Ch ; '\'
0x140008732  lea     rdx, [rsp+468h+TargetPath]
0x14000873a  mov     r8, rsi
0x14000873d  mov     [rsp+rbx*2+468h+var_44A], ax
0x140008742  mov     rcx, rbp
0x140008745  call    BfspFileExistsOnNtDevice
0x14000874a  mov     ebx, eax
0x14000874c  test    eax, eax
0x14000874e  js      short loc_14000876D
0x140008750  cmp     dword ptr [rsi], 1
0x140008753  jz      short loc_14000876D
0x140008755  mov     r8d, 104h; cchBufferLength
0x14000875b  lea     rdx, [rsp+468h+szVolumeName]; lpszVolumeName
0x140008760  mov     rcx, rdi; hFindVolume
0x140008763  call    cs:__imp_FindNextVolumeW
0x140008769  test    eax, eax
0x14000876b  jnz     short loc_1400086FB
0x14000876d  mov     rcx, rdi; hFindVolume
0x140008770  call    cs:__imp_FindVolumeClose
0x140008776  mov     eax, ebx
0x140008778  mov     rcx, [rsp+468h+var_28]
0x140008780  xor     rcx, rsp; StackCookie
0x140008783  call    __security_check_cookie
0x140008788  lea     r11, [rsp+468h+var_18]
0x140008790  mov     rbx, [r11+30h]
0x140008794  mov     rbp, [r11+38h]
0x140008798  mov     rsp, r11
0x14000879b  pop     r14
0x14000879d  pop     rdi
0x14000879e  pop     rsi
0x14000879f  retn
```
