# SectionGroupNode::GetMetadata(ConfigTreeBase *,ushort const *,tagVARIANT *)

- ea: `0x18000b500`
- end: `0x18000b58c`
- name: `?GetMetadata@SectionGroupNode@@UEAAXPEAVConfigTreeBase@@PEBGPEAUtagVARIANT@@@Z`
- size: `140`
- prototype: `void(SectionGroupNode *__hidden this, struct ConfigTreeBase *, const unsigned __int16 *, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x18000b500`
- `0x180012ea8`
- `0x180012f3c`
- `0x18001307a`
- `0x180014010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall SectionGroupNode::GetMetadata(
        SectionGroupNode *this,
        struct ConfigTreeBase *a2,
        const unsigned __int16 *a3,
        struct tagVARIANT *a4)
{
  __int64 v5; // rdi
  int v6; // eax
  LONGLONG v7; // rax
  _QWORD v8[3]; // [rsp+20h] [rbp-18h] BYREF
  int pExceptionObject; // [rsp+40h] [rbp+8h] BYREF

  v5 = *((_QWORD *)this + 11);
  if ( v5 && !wcscmp_0(a3, L"type") )
  {
    v8[0] = 0;
    v6 = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v5 + 72LL))(v5, v8);
    if ( v6 < 0 )
    {
      pExceptionObject = v6;
      throw (long *)&pExceptionObject;
    }
    a4->vt = 8;
    v7 = v8[0];
    v8[0] = 0;
    a4->llVal = v7;
    ScopedBSTR::Reset((ScopedBSTR *)v8);
  }
}

```

## disassembly

```asm
0x18000b500  mov     [rsp+arg_8], rbx
0x18000b505  push    rdi
0x18000b506  sub     rsp, 30h
0x18000b50a  mov     rbx, r9
0x18000b50d  mov     rdi, [rcx+58h]
0x18000b511  test    rdi, rdi
0x18000b514  jz      short loc_18000B581
0x18000b516  lea     rdx, aType; "type"
0x18000b51d  mov     rcx, r8; String1
0x18000b520  call    wcscmp_0
0x18000b525  test    eax, eax
0x18000b527  jnz     short loc_18000B581
0x18000b529  mov     [rsp+38h+var_18], 0
0x18000b532  mov     rax, [rdi]
0x18000b535  lea     rdx, [rsp+38h+var_18]
0x18000b53a  mov     rcx, rdi
0x18000b53d  mov     rax, [rax+48h]
0x18000b541  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b546  test    eax, eax
0x18000b548  jns     short loc_18000B560
0x18000b54a  mov     [rsp+38h+pExceptionObject], eax
0x18000b54e  lea     rdx, _TI1J; pThrowInfo
0x18000b555  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x18000b55a  call    _CxxThrowException_0
0x18000b560  mov     word ptr [rbx], 8
0x18000b565  mov     rax, [rsp+38h+var_18]
0x18000b56a  mov     [rsp+38h+var_18], 0
0x18000b573  mov     [rbx+8], rax
0x18000b577  lea     rcx, [rsp+38h+var_18]; this
0x18000b57c  call    ?Reset@ScopedBSTR@@QEAAXXZ; ScopedBSTR::Reset(void)
0x18000b581  mov     rbx, [rsp+38h+arg_8]
0x18000b586  add     rsp, 30h
0x18000b58a  pop     rdi
0x18000b58b  retn
```
