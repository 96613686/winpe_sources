# AddUrlToUrlGroup

- ea: `0x180003890`
- end: `0x180003977`
- name: `AddUrlToUrlGroup`
- size: `231`
- prototype: `__int64 __usercall@<rax>(HANDLE FileHandle@<rcx>, __int64, __int64, int)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180003840`
- `0x180003d00`
- `0x180009f28`

## callees

- `0x180002b40`
- `0x180003890`
- `0x18000b214`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180003935`
- `ntdll!RtlNtStatusToDosError` at `0x180003935`
- `ntdll!RtlInitUnicodeStringEx` at `0x180003929`
- `ntdll!RtlInitUnicodeStringEx` at `0x180003929`

## pseudocode

```c
ULONG __fastcall AddUrlToUrlGroup(
        HANDLE FileHandle,
        int a2,
        __int64 a3,
        const WCHAR *a4,
        __int64 a5,
        __int64 a6,
        int a7)
{
  int inited; // eax
  __int128 InputBuffer; // [rsp+50h] [rbp-78h] BYREF
  __int128 v14; // [rsp+60h] [rbp-68h]
  _OWORD DestinationString[5]; // [rsp+70h] [rbp-58h] BYREF

  memset(DestinationString, 0, 28);
  InputBuffer = 0;
  v14 = 0;
  if ( (byte_1800126A3 & 4) != 0 )
    WPP_SF_qdISIqL(
      (_DWORD)FileHandle,
      a2,
      a3,
      (_DWORD)FileHandle,
      a2,
      a3,
      (__int64)a4,
      a5,
      a6,
      a7,
      InputBuffer,
      v14,
      DestinationString[0],
      DestinationString[1]);
  LODWORD(InputBuffer) = a2;
  *((_QWORD *)&InputBuffer + 1) = a3;
  *(_QWORD *)&v14 = a5;
  *(_QWORD *)&DestinationString[0] = a6;
  DWORD2(v14) = a7;
  inited = RtlInitUnicodeStringEx((PUNICODE_STRING)((char *)DestinationString + 8), a4);
  if ( inited >= 0 )
    return HttpApiSynchronousDeviceControl(FileHandle, 0x128020u, &InputBuffer, 0x40u, 0, 0, 0);
  else
    return RtlNtStatusToDosError(inited);
}

```

## disassembly

```asm
0x180003890  push    rbx
0x180003892  push    rbp
0x180003893  push    rsi
0x180003894  push    rdi
0x180003895  push    r12
0x180003897  push    r14
0x180003899  push    r15
0x18000389b  sub     rsp, 90h
0x1800038a2  xorps   xmm0, xmm0
0x1800038a5  mov     rbx, r9
0x1800038a8  movups  [rsp+0C8h+DestinationString], xmm0
0x1800038ad  mov     rdi, r8
0x1800038b0  mov     esi, edx
0x1800038b2  movups  [rsp+0C8h+DestinationString+0Ch], xmm0
0x1800038b7  mov     r12, rcx
0x1800038ba  xor     eax, eax
0x1800038bc  movups  [rsp+0C8h+InputBuffer], xmm0
0x1800038c1  movups  [rsp+0C8h+var_68], xmm0
0x1800038c6  test    cs:byte_1800126A3, 4
0x1800038cd  mov     ebp, [rsp+0C8h+arg_30]
0x1800038d4  mov     r14, [rsp+0C8h+arg_28]
0x1800038dc  mov     r15, [rsp+0C8h+arg_20]
0x1800038e4  jz      short loc_18000390A
0x1800038e6  mov     [rsp+0C8h+var_80], ebp
0x1800038ea  mov     r9, rcx
0x1800038ed  mov     [rsp+0C8h+var_88], r14
0x1800038f2  mov     [rsp+0C8h+var_90], r15
0x1800038f7  mov     [rsp+0C8h+var_98], rbx
0x1800038fc  mov     qword ptr [rsp+0C8h+var_A0], r8
0x180003901  mov     dword ptr [rsp+0C8h+var_A8], edx
0x180003905  call    WPP_SF_qdISIqL
0x18000390a  mov     rdx, rbx; SourceString
0x18000390d  mov     dword ptr [rsp+0C8h+InputBuffer], esi
0x180003911  lea     rcx, [rsp+0C8h+DestinationString+8]; DestinationString
0x180003916  mov     qword ptr [rsp+0C8h+InputBuffer+8], rdi
0x18000391b  mov     qword ptr [rsp+0C8h+var_68], r15
0x180003920  mov     qword ptr [rsp+0C8h+DestinationString], r14
0x180003925  mov     dword ptr [rsp+0C8h+var_68+8], ebp
0x180003929  call    cs:__imp_RtlInitUnicodeStringEx
0x18000392f  test    eax, eax
0x180003931  jns     short loc_18000393D
0x180003933  mov     ecx, eax; Status
0x180003935  call    cs:__imp_RtlNtStatusToDosError
0x18000393b  jmp     short loc_180003965
0x18000393d  xor     eax, eax
0x18000393f  lea     r8, [rsp+0C8h+InputBuffer]; InputBuffer
0x180003944  mov     [rsp+0C8h+var_98], rax; __int64
0x180003949  mov     r9d, 40h ; '@'; InputBufferLength
0x18000394f  mov     [rsp+0C8h+var_A0], eax; ULONG
0x180003953  mov     edx, 128020h; IoControlCode
0x180003958  mov     rcx, r12; FileHandle
0x18000395b  mov     [rsp+0C8h+var_A8], rax; PVOID
0x180003960  call    HttpApiSynchronousDeviceControl
0x180003965  add     rsp, 90h
0x18000396c  pop     r15
0x18000396e  pop     r14
0x180003970  pop     r12
0x180003972  pop     rdi
0x180003973  pop     rsi
0x180003974  pop     rbp
0x180003975  pop     rbx
0x180003976  retn
```
