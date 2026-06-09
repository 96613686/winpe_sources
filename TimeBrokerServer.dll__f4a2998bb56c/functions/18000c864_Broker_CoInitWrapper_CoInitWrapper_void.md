# Broker::CoInitWrapper::CoInitWrapper(void)

- ea: `0x18000c864`
- end: `0x18000c8f2`
- name: `??0CoInitWrapper@Broker@@QEAA@XZ`
- size: `142`
- prototype: `Broker::CoInitWrapper *__fastcall(Broker::CoInitWrapper *this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000c69c`

## callees

- `0x180003800`
- `0x18000c864`
- `0x180013978`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18000c875`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18000c875`

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
0x18000c864  mov     [rsp+arg_0], rbx
0x18000c869  push    rdi
0x18000c86a  sub     rsp, 50h
0x18000c86e  mov     rdi, rcx
0x18000c871  xor     edx, edx; dwCoInit
0x18000c873  xor     ecx, ecx; pvReserved
0x18000c875  call    cs:__imp_CoInitializeEx
0x18000c87b  mov     ebx, eax
0x18000c87d  test    eax, eax
0x18000c87f  js      short loc_18000C88F
0x18000c881  mov     rbx, [rsp+58h+arg_0]
0x18000c886  mov     rax, rdi
0x18000c889  add     rsp, 50h
0x18000c88d  pop     rdi
0x18000c88e  retn
0x18000c88f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c896  test    dword ptr [rcx+1Ch], 400h
0x18000c89d  jz      short loc_18000C8BD
0x18000c89f  cmp     byte ptr [rcx+19h], 2
0x18000c8a3  jb      short loc_18000C8BD
0x18000c8a5  mov     rcx, [rcx+10h]
0x18000c8a9  lea     r8, WPP_a9458e0debc7300a47110d600cc51ede_Traceguids
0x18000c8b0  mov     edx, 0Eh
0x18000c8b5  mov     r9d, ebx
0x18000c8b8  call    WPP_SF_d
0x18000c8bd  lea     rax, ??_7Win32Error@Broker@@6B@; const Broker::Win32Error::`vftable'
0x18000c8c4  mov     [rsp+58h+var_20], 1
0x18000c8cc  mov     [rsp+58h+pExceptionObject], rax
0x18000c8d1  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x18000c8d8  movzx   eax, bx
0x18000c8db  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x18000c8e0  xorps   xmm0, xmm0
0x18000c8e3  mov     [rsp+58h+var_18], eax
0x18000c8e7  movups  [rsp+58h+var_30], xmm0
0x18000c8ec  call    _CxxThrowException_0
```
