# NetSetup2::ObjectCreationTemplate::Create(NetSetup2::details::TransactionBase &,_NETSETUP_OBJECT_TYPE)

- ea: `0x18002ba68`
- end: `0x18002bba0`
- name: `?Create@ObjectCreationTemplate@NetSetup2@@QEAA?AU_GUID@@AEAVTransactionBase@details@2@W4_NETSETUP_OBJECT_TYPE@@@Z`
- size: `312`
- prototype: `_OWORD *__fastcall(__int64 *, _OWORD *, _QWORD *)`
- caller_count: `2`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x18001e734`
- `0x180020384`

## callees

- `0x1800027c0`
- `0x1800032e4`
- `0x180008854`
- `0x18002a5f4`
- `0x18002ba68`
- `0x18002d630`
- `0x18002dff8`

## import_xrefs

- `NetSetupApi!NetSetupCreateObject` at `0x18002bb45`
- `NetSetupApi!NetSetupCreateObject` at `0x18002bb45`

## pseudocode

```c
_OWORD *__fastcall NetSetup2::ObjectCreationTemplate::Create(__int64 *a1, _OWORD *a2, _QWORD *a3)
{
  unsigned __int64 v6; // r8
  __int64 i; // r9
  __int64 v8; // r8
  int Object; // eax
  _BYTE pExceptionObject[208]; // [rsp+30h] [rbp-108h] BYREF
  __int128 v12; // [rsp+100h] [rbp-38h] BYREF
  __int64 v13; // [rsp+110h] [rbp-28h]

  v12 = 0;
  v13 = 0;
  std::vector<_NETSETUPPROPERTY>::_Construct_n<>(&v12, 0xAAAAAAAAAAAAAAABuLL * ((a1[1] - *a1) >> 4));
  v6 = 0;
  for ( i = *a1; v6 < 0xAAAAAAAAAAAAAAABuLL * ((a1[1] - *a1) >> 4); i = *a1 )
  {
    NetSetup2::Property::Store((NetSetup2::Property *)(i + 48 * v6), (struct _NETSETUPPROPERTY *)(48 * v6 + v12));
    v6 = v8 + 1;
  }
  *a2 = 0;
  Object = NetSetupCreateObject(*a3, 2, 0xAAAAAAAAAAAAAAABuLL * ((__int64)(*((_QWORD *)&v12 + 1) - v12) >> 4), v12, a2);
  if ( Object < 0 )
  {
    HResultException::HResultException((HResultException *)pExceptionObject, Object);
    throw (HResultException *)pExceptionObject;
  }
  std::vector<_NETSETUPPROPERTY>::_Tidy(&v12);
  return a2;
}

```

## disassembly

```asm
0x18002ba68  mov     r11, rsp
0x18002ba6b  mov     [r11+20h], rbx
0x18002ba6f  push    rbp
0x18002ba70  push    rsi
0x18002ba71  push    rdi
0x18002ba72  sub     rsp, 120h
0x18002ba79  mov     rax, cs:__security_cookie
0x18002ba80  xor     rax, rsp
0x18002ba83  mov     [rsp+138h+var_20], rax
0x18002ba8b  mov     rsi, r8
0x18002ba8e  mov     rbx, rdx
0x18002ba91  mov     rdi, rcx
0x18002ba94  xorps   xmm0, xmm0
0x18002ba97  movdqu  xmmword ptr [r11-38h], xmm0
0x18002ba9d  mov     qword ptr [r11-28h], 0
0x18002baa5  mov     rdx, [rcx+8]
0x18002baa9  sub     rdx, [rcx]
0x18002baac  sar     rdx, 4
0x18002bab0  mov     rbp, 0AAAAAAAAAAAAAAABh
0x18002baba  imul    rdx, rbp
0x18002babe  lea     rcx, [r11-38h]
0x18002bac2  call    ??$_Construct_n@$$V@?$vector@U_NETSETUPPROPERTY@@V?$allocator@U_NETSETUPPROPERTY@@@std@@@std@@AEAAX_K@Z; std::vector<_NETSETUPPROPERTY>::_Construct_n<>(unsigned __int64)
0x18002bac7  nop
0x18002bac8  xor     r8d, r8d
0x18002bacb  mov     r9, [rdi]
0x18002bace  mov     rax, [rdi+8]
0x18002bad2  sub     rax, r9
0x18002bad5  sar     rax, 4
0x18002bad9  imul    rax, rbp
0x18002badd  test    rax, rax
0x18002bae0  jz      short loc_18002BB17
0x18002bae2  lea     rcx, [r8+r8*2]
0x18002bae6  shl     rcx, 4
0x18002baea  mov     rdx, [rsp+138h+var_38]
0x18002baf2  add     rdx, rcx; struct _NETSETUPPROPERTY *
0x18002baf5  add     rcx, r9; this
0x18002baf8  call    ?Store@Property@NetSetup2@@QEBAXAEAU_NETSETUPPROPERTY@@@Z; NetSetup2::Property::Store(_NETSETUPPROPERTY &)
0x18002bafd  inc     r8
0x18002bb00  mov     r9, [rdi]
0x18002bb03  mov     rax, [rdi+8]
0x18002bb07  sub     rax, r9
0x18002bb0a  sar     rax, 4
0x18002bb0e  imul    rax, rbp
0x18002bb12  cmp     r8, rax
0x18002bb15  jb      short loc_18002BAE2
0x18002bb17  xorps   xmm0, xmm0
0x18002bb1a  movups  xmmword ptr [rbx], xmm0
0x18002bb1d  mov     r9, [rsp+138h+var_38]
0x18002bb25  mov     r8, [rsp+138h+var_30]
0x18002bb2d  sub     r8, r9
0x18002bb30  sar     r8, 4
0x18002bb34  imul    r8, rbp
0x18002bb38  mov     [rsp+138h+var_118], rbx
0x18002bb3d  mov     edx, 2
0x18002bb42  mov     rcx, [rsi]
0x18002bb45  call    cs:__imp_NetSetupCreateObject
0x18002bb4b  test    eax, eax
0x18002bb4d  jns     short loc_18002BB6D
0x18002bb4f  mov     edx, eax; int
0x18002bb51  lea     rcx, [rsp+138h+pExceptionObject]; this
0x18002bb56  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x18002bb5b  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x18002bb62  lea     rcx, [rsp+138h+pExceptionObject]; pExceptionObject
0x18002bb67  call    _CxxThrowException_0
0x18002bb6d  lea     rcx, [rsp+138h+var_38]
0x18002bb75  call    ?_Tidy@?$vector@U_NETSETUPPROPERTY@@V?$allocator@U_NETSETUPPROPERTY@@@std@@@std@@AEAAXXZ; std::vector<_NETSETUPPROPERTY>::_Tidy(void)
0x18002bb7a  mov     rax, rbx
0x18002bb7d  mov     rcx, [rsp+138h+var_20]
0x18002bb85  xor     rcx, rsp; StackCookie
0x18002bb88  call    __security_check_cookie
0x18002bb8d  mov     rbx, [rsp+138h+arg_18]
0x18002bb95  add     rsp, 120h
0x18002bb9c  pop     rdi
0x18002bb9d  pop     rsi
0x18002bb9e  pop     rbp
0x18002bb9f  retn
```
