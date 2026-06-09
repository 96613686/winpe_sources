# RemoveUrlFromUrlGroup

- ea: `0x180001240`
- end: `0x180001325`
- name: `RemoveUrlFromUrlGroup`
- size: `229`
- prototype: `__int64 __usercall@<rax>(HANDLE FileHandle@<rcx>, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800011f0`
- `0x180001490`

## callees

- `0x180001240`
- `0x180002b40`
- `0x18000b30c`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x1800012e6`
- `ntdll!RtlNtStatusToDosError` at `0x1800012e6`
- `ntdll!RtlInitUnicodeStringEx` at `0x1800012da`
- `ntdll!RtlInitUnicodeStringEx` at `0x1800012da`

## pseudocode

```c
ULONG __fastcall RemoveUrlFromUrlGroup(
        HANDLE FileHandle,
        unsigned int a2,
        __int64 a3,
        const WCHAR *a4,
        unsigned int a5)
{
  int inited; // eax
  __int128 InputBuffer; // [rsp+40h] [rbp-78h] BYREF
  __int128 v12; // [rsp+50h] [rbp-68h]
  _UNICODE_STRING DestinationString[5]; // [rsp+60h] [rbp-58h] BYREF

  memset(DestinationString, 0, 28);
  InputBuffer = 0;
  v12 = 0;
  if ( (byte_1800126A3 & 4) != 0 )
    WPP_SF_qdISL(
      (_DWORD)FileHandle,
      a2,
      a3,
      (_DWORD)FileHandle,
      a2,
      a3,
      (__int64)a4,
      a5,
      InputBuffer,
      v12,
      *(_OWORD *)DestinationString,
      *(_OWORD *)&DestinationString[1]);
  *(_QWORD *)&InputBuffer = a2;
  v12 = 0;
  memset(DestinationString, 0, 24);
  *((_QWORD *)&InputBuffer + 1) = a3;
  DestinationString[1].Buffer = (PWSTR)a5;
  inited = RtlInitUnicodeStringEx((PUNICODE_STRING)&DestinationString[0].Buffer, a4);
  if ( inited >= 0 )
    return HttpApiSynchronousDeviceControl(FileHandle, 0x128024u, &InputBuffer, 0x40u, 0, 0, 0);
  else
    return RtlNtStatusToDosError(inited);
}

```

## disassembly

```asm
0x180001240  push    rbx
0x180001242  push    rbp
0x180001243  push    rsi
0x180001244  push    rdi
0x180001245  push    r14
0x180001247  push    r15
0x180001249  sub     rsp, 88h
0x180001250  xorps   xmm0, xmm0
0x180001253  mov     rdi, r9
0x180001256  movups  xmmword ptr [rsp+0B8h+DestinationString.Length], xmm0
0x18000125b  mov     rsi, r8
0x18000125e  mov     ebp, edx
0x180001260  movups  xmmword ptr [rsp+0B8h+DestinationString.Buffer+4], xmm0
0x180001265  mov     rbx, rcx
0x180001268  xor     eax, eax
0x18000126a  movups  [rsp+0B8h+InputBuffer], xmm0
0x18000126f  movups  [rsp+0B8h+var_68], xmm0
0x180001274  test    cs:byte_1800126A3, 4
0x18000127b  mov     r14d, [rsp+0B8h+arg_20]
0x180001283  jz      short loc_1800012A0
0x180001285  mov     [rsp+0B8h+var_80], r14d
0x18000128a  mov     [rsp+0B8h+var_88], r9
0x18000128f  mov     r9, rcx
0x180001292  mov     qword ptr [rsp+0B8h+var_90], r8
0x180001297  mov     dword ptr [rsp+0B8h+var_98], edx
0x18000129b  call    WPP_SF_qdISL
0x1800012a0  xor     r15d, r15d
0x1800012a3  mov     dword ptr [rsp+0B8h+InputBuffer], ebp
0x1800012a7  xorps   xmm0, xmm0
0x1800012aa  mov     dword ptr [rsp+0B8h+InputBuffer+4], r15d
0x1800012af  xorps   xmm1, xmm1
0x1800012b2  movdqa  [rsp+0B8h+var_68], xmm0
0x1800012b8  mov     rdx, rdi; SourceString
0x1800012bb  movdqa  xmmword ptr [rsp+0B8h+DestinationString.Length], xmm1
0x1800012c1  lea     rcx, [rsp+0B8h+DestinationString.Buffer]; DestinationString
0x1800012c6  mov     [rsp+0B8h+var_48], r15
0x1800012cb  mov     [rsp+0B8h+var_3C], r15d
0x1800012d0  mov     qword ptr [rsp+0B8h+InputBuffer+8], rsi
0x1800012d5  mov     [rsp+0B8h+var_40], r14d
0x1800012da  call    cs:__imp_RtlInitUnicodeStringEx
0x1800012e0  test    eax, eax
0x1800012e2  jns     short loc_1800012EE
0x1800012e4  mov     ecx, eax; Status
0x1800012e6  call    cs:__imp_RtlNtStatusToDosError
0x1800012ec  jmp     short loc_180001315
0x1800012ee  mov     [rsp+0B8h+var_88], r15; __int64
0x1800012f3  lea     r8, [rsp+0B8h+InputBuffer]; InputBuffer
0x1800012f8  mov     [rsp+0B8h+var_90], r15d; ULONG
0x1800012fd  mov     r9d, 40h ; '@'; InputBufferLength
0x180001303  mov     edx, 128024h; IoControlCode
0x180001308  mov     [rsp+0B8h+var_98], r15; PVOID
0x18000130d  mov     rcx, rbx; FileHandle
0x180001310  call    HttpApiSynchronousDeviceControl
0x180001315  add     rsp, 88h
0x18000131c  pop     r15
0x18000131e  pop     r14
0x180001320  pop     rdi
0x180001321  pop     rsi
0x180001322  pop     rbp
0x180001323  pop     rbx
0x180001324  retn
```
