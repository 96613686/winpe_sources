# Broker::CoInitWrapper::CoInitWrapper(void)

- ea: `0x1800111d4`
- end: `0x180011262`
- name: `??0CoInitWrapper@Broker@@QEAA@XZ`
- size: `142`
- prototype: `__int64 __fastcall(Broker::CoInitWrapper *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000c970`
- `0x1800110a0`
- `0x180016950`

## callees

- `0x180009e94`
- `0x1800111d4`
- `0x1800165da`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800111e5`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800111e5`

## pseudocode

```c
Broker::CoInitWrapper *__fastcall Broker::CoInitWrapper::CoInitWrapper(Broker::CoInitWrapper *this)
{
  HRESULT v2; // eax
  unsigned __int16 v3; // bx
  void **pExceptionObject; // [rsp+20h] [rbp-38h] BYREF
  __int128 v6; // [rsp+28h] [rbp-30h]
  int v7; // [rsp+38h] [rbp-20h]
  int v8; // [rsp+40h] [rbp-18h]

  v2 = CoInitializeEx(0, 0);
  v3 = v2;
  if ( v2 < 0 )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        14,
        &WPP_a9458e0debc7300a47110d600cc51ede_Traceguids,
        (unsigned int)v2);
    v7 = 1;
    pExceptionObject = &Broker::Win32Error::`vftable';
    v8 = v3;
    v6 = 0;
    throw (Broker::Win32Error *)&pExceptionObject;
  }
  return this;
}

```

## disassembly

```asm
0x1800111d4  mov     [rsp+arg_0], rbx
0x1800111d9  push    rdi
0x1800111da  sub     rsp, 50h
0x1800111de  mov     rdi, rcx
0x1800111e1  xor     edx, edx; dwCoInit
0x1800111e3  xor     ecx, ecx; pvReserved
0x1800111e5  call    cs:__imp_CoInitializeEx
0x1800111eb  mov     ebx, eax
0x1800111ed  test    eax, eax
0x1800111ef  js      short loc_1800111FF
0x1800111f1  mov     rbx, [rsp+58h+arg_0]
0x1800111f6  mov     rax, rdi
0x1800111f9  add     rsp, 50h
0x1800111fd  pop     rdi
0x1800111fe  retn
0x1800111ff  mov     rcx, cs:WPP_GLOBAL_Control
0x180011206  test    dword ptr [rcx+1Ch], 400h
0x18001120d  jz      short loc_18001122D
0x18001120f  cmp     byte ptr [rcx+19h], 2
0x180011213  jb      short loc_18001122D
0x180011215  mov     rcx, [rcx+10h]
0x180011219  lea     r8, WPP_a9458e0debc7300a47110d600cc51ede_Traceguids
0x180011220  mov     edx, 0Eh
0x180011225  mov     r9d, ebx
0x180011228  call    WPP_SF_d
0x18001122d  lea     rax, ??_7Win32Error@Broker@@6B@; const Broker::Win32Error::`vftable'
0x180011234  mov     [rsp+58h+var_20], 1
0x18001123c  mov     [rsp+58h+pExceptionObject], rax
0x180011241  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x180011248  movzx   eax, bx
0x18001124b  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x180011250  xorps   xmm0, xmm0
0x180011253  mov     [rsp+58h+var_18], eax
0x180011257  movups  [rsp+58h+var_30], xmm0
0x18001125c  call    _CxxThrowException_0
```
