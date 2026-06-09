# Broker::SebBroker::QueryEventPackage(_GUID const &,ushort * *)

- ea: `0x18000f440`
- end: `0x18000f67a`
- name: `?QueryEventPackage@SebBroker@Broker@@QEAAXAEBU_GUID@@PEAPEAG@Z`
- size: `570`
- prototype: `void __fastcall(Broker::SebBroker *__hidden this, const struct _GUID *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180002d10`

## callees

- `0x180005a50`
- `0x180008c00`
- `0x18000e79c`
- `0x18000f440`
- `0x180011590`
- `0x18001d9ac`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000f59f`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000f59f`
- `BrokerLib!BrFindBrokeredEvent` at `0x18000f566`
- `BrokerLib!BrFindBrokeredEvent` at `0x18000f566`
- `BrokerLib!BrGetPackageFullNameForBrokeredEvent` at `0x18000f5ef`
- `BrokerLib!BrGetPackageFullNameForBrokeredEvent` at `0x18000f5ef`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall Broker::SebBroker::QueryEventPackage(
        Broker::SebBroker *this,
        const struct _GUID *a2,
        unsigned __int16 **a3)
{
  unsigned __int16 *v6; // rax
  int PackageFullNameForBrokeredEvent; // eax
  __int64 v8; // [rsp+30h] [rbp-19h] BYREF
  __int64 v9; // [rsp+38h] [rbp-11h]
  _BYTE pExceptionObject[24]; // [rsp+40h] [rbp-9h] BYREF
  int v11; // [rsp+58h] [rbp+Fh]
  int v12; // [rsp+60h] [rbp+17h]
  __int128 v13; // [rsp+70h] [rbp+27h]
  __int128 v14; // [rsp+80h] [rbp+37h]
  __int64 v15; // [rsp+C0h] [rbp+77h] BYREF

  v15 = 0;
  v13 = 0;
  v14 = 0;
  if ( !a3 )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, &WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids);
    *(_OWORD *)&pExceptionObject[8] = 0;
    v11 = 4;
    *(_QWORD *)pExceptionObject = &Broker::InvalidParameter::`vftable';
    throw (Broker::InvalidParameter *)pExceptionObject;
  }
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF__guid_(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, &WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids, a2);
  if ( !*((_QWORD *)this + 17) )
  {
    *(_OWORD *)&pExceptionObject[8] = 0;
    v11 = 3;
    *(_QWORD *)pExceptionObject = &Broker::NotFound::`vftable';
    throw (Broker::NotFound *)pExceptionObject;
  }
  v8 = *((_QWORD *)this + 17);
  v9 = 1;
  Broker::BrokerLock::Acquire((Broker::BrokerLock *)&v8);
  *(struct _GUID *)pExceptionObject = *a2;
  if ( (unsigned int)BrFindBrokeredEvent(*((_QWORD *)this + 17), pExceptionObject, 0, 0, &v15) )
  {
    *(_OWORD *)&pExceptionObject[8] = 0;
    v11 = 3;
    *(_QWORD *)pExceptionObject = &Broker::NotFound::`vftable';
    throw (Broker::NotFound *)pExceptionObject;
  }
  v6 = (unsigned __int16 *)malloc(0x800u);
  *a3 = v6;
  if ( !v6 )
  {
    *(_QWORD *)&pExceptionObject[16] = 0;
    *(_QWORD *)&pExceptionObject[8] = "bad allocation";
    *(_QWORD *)pExceptionObject = &std::bad_alloc::`vftable';
    throw (std::bad_alloc *)pExceptionObject;
  }
  PackageFullNameForBrokeredEvent = BrGetPackageFullNameForBrokeredEvent(*((_QWORD *)this + 17), v15, 2048, v6);
  if ( PackageFullNameForBrokeredEvent )
  {
    *(_OWORD *)&pExceptionObject[8] = 0;
    v11 = 1;
    *(_QWORD *)pExceptionObject = &Broker::Win32Error::`vftable';
    v12 = PackageFullNameForBrokeredEvent;
    throw (Broker::Win32Error *)pExceptionObject;
  }
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF__guid_(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, &WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids, a2);
  if ( HIDWORD(v9) )
    Broker::BrokerLock::Release((Broker::BrokerLock *)&v8);
}

```

## disassembly

```asm
0x18000f440  mov     [rsp-8+arg_0], rbx
0x18000f445  mov     [rsp-8+arg_8], rsi
0x18000f44a  push    rbp
0x18000f44b  push    rdi
0x18000f44c  push    r14
0x18000f44e  lea     rbp, [rsp-47h]
0x18000f453  sub     rsp, 90h
0x18000f45a  mov     rdi, r8
0x18000f45d  mov     rsi, rdx
0x18000f460  mov     rbx, rcx
0x18000f463  xor     r14d, r14d
0x18000f466  mov     [rbp+57h+arg_10], r14
0x18000f46a  xorps   xmm0, xmm0
0x18000f46d  movdqu  [rbp+57h+var_30], xmm0
0x18000f472  movdqu  [rbp+57h+var_20], xmm0
0x18000f477  test    r8, r8
0x18000f47a  jnz     short loc_18000F4CE
0x18000f47c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f483  test    byte ptr [rcx+1Ch], 20h
0x18000f487  jz      short loc_18000F4A4
0x18000f489  cmp     byte ptr [rcx+19h], 2
0x18000f48d  jb      short loc_18000F4A4
0x18000f48f  mov     edx, 1Dh
0x18000f494  lea     r8, WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids
0x18000f49b  mov     rcx, [rcx+10h]
0x18000f49f  call    WPP_SF_
0x18000f4a4  xorps   xmm0, xmm0
0x18000f4a7  movups  xmmword ptr [rbp+57h+pExceptionObject+8], xmm0
0x18000f4ab  mov     [rbp+57h+var_48], 4
0x18000f4b2  lea     rax, ??_7InvalidParameter@Broker@@6B@; const Broker::InvalidParameter::`vftable'
0x18000f4b9  mov     qword ptr [rbp+57h+pExceptionObject], rax
0x18000f4bd  lea     rdx, _TI3?AUInvalidParameter@Broker@@; pThrowInfo
0x18000f4c4  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18000f4c8  call    _CxxThrowException_0
0x18000f4ce  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f4d5  test    byte ptr [rcx+1Ch], 1
0x18000f4d9  jz      short loc_18000F4F9
0x18000f4db  cmp     byte ptr [rcx+19h], 4
0x18000f4df  jb      short loc_18000F4F9
0x18000f4e1  mov     edx, 1Eh
0x18000f4e6  mov     r9, rsi
0x18000f4e9  lea     r8, WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids
0x18000f4f0  mov     rcx, [rcx+10h]
0x18000f4f4  call    WPP_SF__guid_
0x18000f4f9  mov     rax, [rbx+88h]
0x18000f500  test    rax, rax
0x18000f503  jnz     short loc_18000F52F
0x18000f505  xorps   xmm0, xmm0
0x18000f508  movups  xmmword ptr [rbp+57h+pExceptionObject+8], xmm0
0x18000f50c  mov     [rbp+57h+var_48], 3
0x18000f513  lea     rax, ??_7NotFound@Broker@@6B@; const Broker::NotFound::`vftable'
0x18000f51a  mov     qword ptr [rbp+57h+pExceptionObject], rax
0x18000f51e  lea     rdx, _TI3?AUNotFound@Broker@@; pThrowInfo
0x18000f525  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18000f529  call    _CxxThrowException_0
0x18000f52f  mov     [rbp+57h+var_70], rax
0x18000f533  mov     [rbp+57h+var_68], 1
0x18000f53b  lea     rcx, [rbp+57h+var_70]; this
0x18000f53f  call    ?Acquire@BrokerLock@Broker@@QEAAXXZ; Broker::BrokerLock::Acquire(void)
0x18000f544  nop
0x18000f545  movups  xmm0, xmmword ptr [rsi]
0x18000f548  movaps  xmmword ptr [rbp+57h+pExceptionObject], xmm0
0x18000f54c  lea     rax, [rbp+57h+arg_10]
0x18000f550  mov     [rsp+0A0h+var_80], rax
0x18000f555  xor     r9d, r9d
0x18000f558  xor     r8d, r8d
0x18000f55b  lea     rdx, [rbp+57h+pExceptionObject]
0x18000f55f  mov     rcx, [rbx+88h]
0x18000f566  call    cs:__imp_BrFindBrokeredEvent
0x18000f56c  test    eax, eax
0x18000f56e  jz      short loc_18000F59A
0x18000f570  xorps   xmm0, xmm0
0x18000f573  movups  xmmword ptr [rbp+57h+pExceptionObject+8], xmm0
0x18000f577  mov     [rbp+57h+var_48], 3
0x18000f57e  lea     rax, ??_7NotFound@Broker@@6B@; const Broker::NotFound::`vftable'
0x18000f585  mov     qword ptr [rbp+57h+pExceptionObject], rax
0x18000f589  lea     rdx, _TI3?AUNotFound@Broker@@; pThrowInfo
0x18000f590  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18000f594  call    _CxxThrowException_0
0x18000f59a  mov     ecx, 800h; Size
0x18000f59f  call    cs:__imp_malloc
0x18000f5a5  mov     [rdi], rax
0x18000f5a8  test    rax, rax
0x18000f5ab  jnz     short loc_18000F5DB
0x18000f5ad  xorps   xmm0, xmm0
0x18000f5b0  movups  xmmword ptr [rbp+57h+pExceptionObject+8], xmm0
0x18000f5b4  lea     rax, aBadAllocation; "bad allocation"
0x18000f5bb  mov     qword ptr [rbp+57h+pExceptionObject+8], rax
0x18000f5bf  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x18000f5c6  mov     qword ptr [rbp+57h+pExceptionObject], rax
0x18000f5ca  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18000f5d1  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18000f5d5  call    _CxxThrowException_0
0x18000f5db  mov     r9, rax
0x18000f5de  mov     r8d, 800h
0x18000f5e4  mov     rdx, [rbp+57h+arg_10]
0x18000f5e8  mov     rcx, [rbx+88h]
0x18000f5ef  call    cs:__imp_BrGetPackageFullNameForBrokeredEvent
0x18000f5f5  test    eax, eax
0x18000f5f7  jz      short loc_18000F626
0x18000f5f9  xorps   xmm0, xmm0
0x18000f5fc  movups  xmmword ptr [rbp+57h+pExceptionObject+8], xmm0
0x18000f600  mov     [rbp+57h+var_48], 1
0x18000f607  lea     rcx, ??_7Win32Error@Broker@@6B@; const Broker::Win32Error::`vftable'
0x18000f60e  mov     qword ptr [rbp+57h+pExceptionObject], rcx
0x18000f612  mov     [rbp+57h+var_40], eax
0x18000f615  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x18000f61c  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18000f620  call    _CxxThrowException_0
0x18000f626  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f62d  test    byte ptr [rcx+1Ch], 1
0x18000f631  jz      short loc_18000F652
0x18000f633  cmp     byte ptr [rcx+19h], 4
0x18000f637  jb      short loc_18000F652
0x18000f639  mov     edx, 1Fh
0x18000f63e  mov     r9, rsi
0x18000f641  lea     r8, WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids
0x18000f648  mov     rcx, [rcx+10h]
0x18000f64c  call    WPP_SF__guid_
0x18000f651  nop
0x18000f652  cmp     dword ptr [rbp+57h+var_68+4], 0
0x18000f656  jz      short loc_18000F662
0x18000f658  lea     rcx, [rbp+57h+var_70]; this
0x18000f65c  call    ?Release@BrokerLock@Broker@@QEAAXXZ; Broker::BrokerLock::Release(void)
0x18000f661  nop
0x18000f662  lea     r11, [rsp+0A0h+var_10]
0x18000f66a  mov     rbx, [r11+20h]
0x18000f66e  mov     rsi, [r11+28h]
0x18000f672  mov     rsp, r11
0x18000f675  pop     r14
0x18000f677  pop     rdi
0x18000f678  pop     rbp
0x18000f679  retn
```
