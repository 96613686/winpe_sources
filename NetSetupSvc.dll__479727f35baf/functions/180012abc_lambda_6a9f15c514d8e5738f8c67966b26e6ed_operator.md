# _lambda_6a9f15c514d8e5738f8c67966b26e6ed_::operator()

- ea: `0x180012abc`
- end: `0x180012c4a`
- name: `_lambda_6a9f15c514d8e5738f8c67966b26e6ed_::operator()`
- size: `398`
- prototype: `__int64 __fastcall(unsigned int *, NetSetup2::Exception *)`
- caller_count: `1`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180010ffc`

## callees

- `0x1800032e4`
- `0x1800078d0`
- `0x1800078f8`
- `0x180008854`
- `0x180012abc`
- `0x180013acc`
- `0x180013bbc`
- `0x18001703c`
- `0x18001740c`
- `0x18001984c`
- `0x180019d40`

## import_xrefs

- `NetSetupApi!NetSetupCreateObject` at `0x180012ba8`
- `NetSetupApi!NetSetupCreateObject` at `0x180012ba8`

## pseudocode

```c
__int64 __fastcall lambda_6a9f15c514d8e5738f8c67966b26e6ed_::operator()(unsigned int *a1, NetSetup2::Exception *a2)
{
  NETSETUP_RPC_CONTEXT **v3; // rdi
  __int64 v5; // rdx
  const struct _NETSETUP_OBJECT_ID *v6; // r8
  const struct _NETSETUPPROPERTY *v7; // r14
  unsigned int v8; // r15d
  unsigned int v9; // edi
  __int64 result; // rax
  int v11; // ebp
  unsigned int v12; // [rsp+30h] [rbp-128h] BYREF
  __int128 v13; // [rsp+34h] [rbp-124h]
  _BYTE pExceptionObject[272]; // [rsp+48h] [rbp-110h] BYREF

  v3 = (NETSETUP_RPC_CONTEXT **)(a1 + 4);
  if ( (unsigned __int8)IsOSComponentFlagSetInProperties(*a1, *((_QWORD *)a1 + 1))
    && !NETSETUP_RPC_CONTEXT::IsCalledFromServicingStack(*v3) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_d7c9c24d725337bc8e6af9dd6d1b553a_Traceguids);
    v12 = a1[6];
    v13 = *(_OWORD *)*((_QWORD *)a1 + 4);
    NetSetup2::Exception::throw_NotAllowedToCreateOSComponent(a2, (struct HNETSETUP__ *)&v12, v6);
  }
  *((_BYTE *)*v3 + 56) = 1;
  if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    v7 = (const struct _NETSETUPPROPERTY *)*((_QWORD *)a1 + 1);
    v8 = *a1;
    v9 = *((_DWORD *)*v3 + 13);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      WPP_SF_LL(*((_QWORD *)WPP_GLOBAL_Control + 2), v5, v6, v9, a1[6]);
    TraceProperties(v9, v8, v7);
    v3 = (NETSETUP_RPC_CONTEXT **)(a1 + 4);
  }
  result = NetSetupCreateObject(a2, a1[6], *a1, *((_QWORD *)a1 + 1), *((_QWORD *)a1 + 4));
  v11 = result;
  if ( (int)result < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        22,
        WPP_d7c9c24d725337bc8e6af9dd6d1b553a_Traceguids,
        (unsigned int)result);
    HResultException::HResultException((HResultException *)pExceptionObject, v11);
    throw (HResultException *)pExceptionObject;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    return WPP_SF_LL_guid_(
             *((_QWORD *)WPP_GLOBAL_Control + 2),
             23,
             (unsigned int)WPP_d7c9c24d725337bc8e6af9dd6d1b553a_Traceguids,
             *((_DWORD *)*v3 + 13),
             a1[6],
             *((_QWORD *)a1 + 4));
  return result;
}

```

## disassembly

```asm
0x180012abc  push    rbx
0x180012abe  push    rbp
0x180012abf  push    rsi
0x180012ac0  push    rdi
0x180012ac1  push    r14
0x180012ac3  push    r15
0x180012ac5  sub     rsp, 128h
0x180012acc  mov     rbp, rdx
0x180012acf  lea     rdi, [rcx+10h]
0x180012ad3  mov     rdx, [rcx+8]
0x180012ad7  mov     rbx, rcx
0x180012ada  mov     ecx, [rcx]
0x180012adc  call    IsOSComponentFlagSetInProperties
0x180012ae1  test    al, al
0x180012ae3  jz      short loc_180012B41
0x180012ae5  mov     rcx, [rdi]; this
0x180012ae8  call    ?IsCalledFromServicingStack@NETSETUP_RPC_CONTEXT@@QEAA_NXZ; NETSETUP_RPC_CONTEXT::IsCalledFromServicingStack(void)
0x180012aed  test    al, al
0x180012aef  jnz     short loc_180012B41
0x180012af1  mov     rcx, cs:WPP_GLOBAL_Control
0x180012af8  lea     rsi, WPP_GLOBAL_Control
0x180012aff  cmp     rcx, rsi
0x180012b02  jz      short loc_180012B1F
0x180012b04  cmp     byte ptr [rcx+19h], 2
0x180012b08  jb      short loc_180012B1F
0x180012b0a  mov     rcx, [rcx+10h]
0x180012b0e  lea     r8, WPP_d7c9c24d725337bc8e6af9dd6d1b553a_Traceguids
0x180012b15  mov     edx, 15h
0x180012b1a  call    WPP_SF_
0x180012b1f  mov     eax, [rbx+18h]
0x180012b22  lea     rdx, [rsp+158h+var_128]; struct HNETSETUP__ *
0x180012b27  mov     [rsp+158h+var_128], eax
0x180012b2b  mov     rcx, rbp; this
0x180012b2e  mov     rax, [rbx+20h]
0x180012b32  movups  xmm0, xmmword ptr [rax]
0x180012b35  movdqu  [rsp+158h+var_124], xmm0
0x180012b3b  call    ?throw_NotAllowedToCreateOSComponent@Exception@NetSetup2@@YAXPEAUHNETSETUP__@@AEBU_NETSETUP_OBJECT_ID@@@Z; NetSetup2::Exception::throw_NotAllowedToCreateOSComponent(HNETSETUP__ *,_NETSETUP_OBJECT_ID const &)
0x180012b41  mov     rax, [rdi]
0x180012b44  lea     rsi, WPP_GLOBAL_Control
0x180012b4b  mov     byte ptr [rax+38h], 1
0x180012b4f  mov     rcx, cs:WPP_GLOBAL_Control
0x180012b56  cmp     byte ptr [rcx+19h], 4
0x180012b5a  jb      short loc_180012B92
0x180012b5c  mov     rax, [rdi]
0x180012b5f  mov     r14, [rbx+8]
0x180012b63  mov     r15d, [rbx]
0x180012b66  mov     edi, [rax+34h]
0x180012b69  cmp     rcx, rsi
0x180012b6c  jz      short loc_180012B81
0x180012b6e  mov     eax, [rbx+18h]
0x180012b71  mov     r9d, edi
0x180012b74  mov     rcx, [rcx+10h]
0x180012b78  mov     dword ptr [rsp+158h+var_138], eax
0x180012b7c  call    WPP_SF_LL
0x180012b81  mov     r8, r14; struct _NETSETUPPROPERTY *
0x180012b84  mov     edx, r15d; unsigned int
0x180012b87  mov     ecx, edi; unsigned int
0x180012b89  call    ?TraceProperties@@YAXIKPEBU_NETSETUPPROPERTY@@@Z; TraceProperties(uint,ulong,_NETSETUPPROPERTY const *)
0x180012b8e  lea     rdi, [rbx+10h]
0x180012b92  mov     rax, [rbx+20h]
0x180012b96  mov     rcx, rbp
0x180012b99  mov     r9, [rbx+8]
0x180012b9d  mov     r8d, [rbx]
0x180012ba0  mov     edx, [rbx+18h]
0x180012ba3  mov     [rsp+158h+var_138], rax
0x180012ba8  call    cs:__imp_NetSetupCreateObject
0x180012bae  mov     ebp, eax
0x180012bb0  test    eax, eax
0x180012bb2  jns     short loc_180012BFC
0x180012bb4  mov     rcx, cs:WPP_GLOBAL_Control
0x180012bbb  cmp     rcx, rsi
0x180012bbe  jz      short loc_180012BDE
0x180012bc0  cmp     byte ptr [rcx+19h], 2
0x180012bc4  jb      short loc_180012BDE
0x180012bc6  mov     rcx, [rcx+10h]
0x180012bca  lea     r8, WPP_d7c9c24d725337bc8e6af9dd6d1b553a_Traceguids
0x180012bd1  mov     edx, 16h
0x180012bd6  mov     r9d, eax
0x180012bd9  call    WPP_SF_d
0x180012bde  mov     edx, ebp; int
0x180012be0  lea     rcx, [rsp+158h+pExceptionObject]; this
0x180012be5  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x180012bea  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x180012bf1  lea     rcx, [rsp+158h+pExceptionObject]; pExceptionObject
0x180012bf6  call    _CxxThrowException_0
0x180012bfc  mov     rcx, cs:WPP_GLOBAL_Control
0x180012c03  cmp     rcx, rsi
0x180012c06  jz      short loc_180012C3A
0x180012c08  cmp     byte ptr [rcx+19h], 4
0x180012c0c  jb      short loc_180012C3A
0x180012c0e  mov     rax, [rbx+20h]
0x180012c12  lea     r8, WPP_d7c9c24d725337bc8e6af9dd6d1b553a_Traceguids
0x180012c19  mov     r9, [rdi]
0x180012c1c  mov     edx, 17h
0x180012c21  mov     rcx, [rcx+10h]
0x180012c25  mov     [rsp+158h+var_130], rax
0x180012c2a  mov     eax, [rbx+18h]
0x180012c2d  mov     r9d, [r9+34h]
0x180012c31  mov     dword ptr [rsp+158h+var_138], eax
0x180012c35  call    WPP_SF_LL_guid_
0x180012c3a  add     rsp, 128h
0x180012c41  pop     r15
0x180012c43  pop     r14
0x180012c45  pop     rdi
0x180012c46  pop     rsi
0x180012c47  pop     rbp
0x180012c48  pop     rbx
0x180012c49  retn
```
