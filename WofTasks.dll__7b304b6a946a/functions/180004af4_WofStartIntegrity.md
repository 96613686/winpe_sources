# WofStartIntegrity

- ea: `0x180004af4`
- end: `0x180004bb7`
- name: `WofStartIntegrity`
- size: `195`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180002474`

## callees

- `0x180004af4`
- `0x180004c4c`
- `0x180004ef4`
- `0x1800051c0`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180004b94`
- `KERNEL32!CloseHandle` at `0x180004b94`

## pseudocode

```c
__int64 __fastcall WofStartIntegrity(__int64 a1)
{
  signed int v2; // esi
  HANDLE hObject; // [rsp+40h] [rbp-38h] BYREF
  DWORD v5; // [rsp+48h] [rbp-30h] BYREF
  int v6[4]; // [rsp+50h] [rbp-28h] BYREF

  v5 = 0;
  hObject = (HANDLE)-1LL;
  *(_OWORD *)v6 = 0;
  v2 = WofpOpenSystemVolumeWithFlagsAndAttributes(0x80u, (__int64 *)&hObject);
  if ( v2 >= 0 )
  {
    *(_QWORD *)&v6[2] = a1;
    v6[0] = 1;
    v6[1] = 1;
    v2 = WofpDeviceIoControl(hObject, 0x90320u, v6, 0x10u, 0, 0, &v5);
  }
  if ( hObject != (HANDLE)-1LL )
    CloseHandle(hObject);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180004af4  mov     [rsp+arg_8], rbx
0x180004af9  push    rsi
0x180004afa  sub     rsp, 70h
0x180004afe  mov     rax, cs:__security_cookie
0x180004b05  xor     rax, rsp
0x180004b08  mov     [rsp+78h+var_18], rax
0x180004b0d  mov     rbx, rcx
0x180004b10  mov     [rsp+78h+var_30], 0
0x180004b18  xorps   xmm0, xmm0
0x180004b1b  mov     [rsp+78h+hObject], 0FFFFFFFFFFFFFFFFh
0x180004b24  mov     ecx, 80h
0x180004b29  lea     rdx, [rsp+78h+hObject]
0x180004b2e  movups  xmmword ptr [rsp+78h+var_28], xmm0
0x180004b33  call    WofpOpenSystemVolumeWithFlagsAndAttributes
0x180004b38  mov     esi, eax
0x180004b3a  test    eax, eax
0x180004b3c  js      short loc_180004B87
0x180004b3e  mov     rcx, [rsp+78h+hObject]; int
0x180004b43  lea     r8, [rsp+78h+var_28]; int
0x180004b48  mov     eax, 1
0x180004b4d  mov     qword ptr [rsp+78h+var_28+8], rbx
0x180004b52  mov     [rsp+78h+var_28], eax
0x180004b56  mov     r9d, 10h; int
0x180004b5c  mov     [rsp+78h+var_28+4], eax
0x180004b60  mov     edx, 90320h; int
0x180004b65  lea     rax, [rsp+78h+var_30]
0x180004b6a  mov     [rsp+78h+var_48], rax; LPDWORD
0x180004b6f  mov     [rsp+78h+var_50], 0; DWORD
0x180004b77  mov     [rsp+78h+var_58], 0; LPVOID
0x180004b80  call    WofpDeviceIoControl
0x180004b85  mov     esi, eax
0x180004b87  cmp     [rsp+78h+hObject], 0FFFFFFFFFFFFFFFFh
0x180004b8d  jz      short loc_180004B9A
0x180004b8f  mov     rcx, [rsp+78h+hObject]; hObject
0x180004b94  call    cs:__imp_CloseHandle
0x180004b9a  mov     eax, esi
0x180004b9c  mov     rcx, [rsp+78h+var_18]
0x180004ba1  xor     rcx, rsp; StackCookie
0x180004ba4  call    __security_check_cookie
0x180004ba9  mov     rbx, [rsp+78h+arg_8]
0x180004bb1  add     rsp, 70h
0x180004bb5  pop     rsi
0x180004bb6  retn
```
