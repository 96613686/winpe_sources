# Broker::CoInitWrapper::CoInitWrapper(void)

- ea: `0x1800147c8`
- end: `0x180014856`
- name: `??0CoInitWrapper@Broker@@QEAA@XZ`
- size: `142`
- prototype: `Broker::CoInitWrapper *__fastcall(Broker::CoInitWrapper *this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180014618`

## callees

- `0x1800030e0`
- `0x1800147c8`
- `0x18001d9ac`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800147d9`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800147d9`

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
0x1800147c8  mov     [rsp+arg_0], rbx
0x1800147cd  push    rdi
0x1800147ce  sub     rsp, 50h
0x1800147d2  mov     rdi, rcx
0x1800147d5  xor     edx, edx; dwCoInit
0x1800147d7  xor     ecx, ecx; pvReserved
0x1800147d9  call    cs:__imp_CoInitializeEx
0x1800147df  mov     ebx, eax
0x1800147e1  test    eax, eax
0x1800147e3  jns     short loc_180014848
0x1800147e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800147ec  test    dword ptr [rcx+1Ch], 400h
0x1800147f3  jz      short loc_180014813
0x1800147f5  cmp     byte ptr [rcx+19h], 2
0x1800147f9  jb      short loc_180014813
0x1800147fb  mov     rcx, [rcx+10h]
0x1800147ff  lea     r8, WPP_a9458e0debc7300a47110d600cc51ede_Traceguids
0x180014806  mov     edx, 0Eh
0x18001480b  mov     r9d, eax
0x18001480e  call    WPP_SF_d
0x180014813  lea     rax, ??_7Win32Error@Broker@@6B@; const Broker::Win32Error::`vftable'
0x18001481a  mov     [rsp+58h+var_20], 1
0x180014822  mov     [rsp+58h+pExceptionObject], rax
0x180014827  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x18001482e  movzx   eax, bx
0x180014831  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x180014836  xorps   xmm0, xmm0
0x180014839  mov     [rsp+58h+var_18], eax
0x18001483d  movups  [rsp+58h+var_30], xmm0
0x180014842  call    _CxxThrowException_0
0x180014848  mov     rbx, [rsp+58h+arg_0]
0x18001484d  mov     rax, rdi
0x180014850  add     rsp, 50h
0x180014854  pop     rdi
0x180014855  retn
```
