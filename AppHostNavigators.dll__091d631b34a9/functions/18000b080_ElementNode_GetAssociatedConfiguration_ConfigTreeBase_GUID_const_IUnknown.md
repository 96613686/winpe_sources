# ElementNode::GetAssociatedConfiguration(ConfigTreeBase *,_GUID const &,IUnknown * *)

- ea: `0x18000b080`
- end: `0x18000b0dc`
- name: `?GetAssociatedConfiguration@ElementNode@@UEAAXPEAVConfigTreeBase@@AEBU_GUID@@PEAPEAUIUnknown@@@Z`
- size: `92`
- prototype: `void __fastcall(ElementNode *__hidden this, struct ConfigTreeBase *, const struct _GUID *, struct IUnknown **)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000b180`

## callees

- `0x1800021a4`
- `0x18000b080`
- `0x180014010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ElementNode::GetAssociatedConfiguration(
        ElementNode *this,
        struct ConfigTreeBase *a2,
        const struct _GUID *a3,
        struct IUnknown **a4)
{
  __int64 v5; // rax
  struct IUnknown *v6; // rax
  __int64 v7[3]; // [rsp+20h] [rbp-18h] BYREF

  v5 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&GUID_64ff8ccc_b287_4dae_b08a_a72cbf45f453.Data1;
  if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&GUID_64ff8ccc_b287_4dae_b08a_a72cbf45f453.Data1 )
    v5 = *(_QWORD *)a3->Data4 - *(_QWORD *)GUID_64ff8ccc_b287_4dae_b08a_a72cbf45f453.Data4;
  if ( !v5 )
  {
    v7[0] = 0;
    (*(void (__fastcall **)(ElementNode *, struct ConfigTreeBase *, __int64 *))(*(_QWORD *)this + 112LL))(this, a2, v7);
    v6 = (struct IUnknown *)v7[0];
    v7[0] = 0;
    *a4 = v6;
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v7);
  }
}

```

## disassembly

```asm
0x18000b080  push    rbx
0x18000b082  sub     rsp, 30h
0x18000b086  mov     rbx, r9
0x18000b089  mov     rax, [r8]
0x18000b08c  sub     rax, qword ptr cs:_GUID_64ff8ccc_b287_4dae_b08a_a72cbf45f453.Data1
0x18000b093  jnz     short loc_18000B0A0
0x18000b095  mov     rax, [r8+8]
0x18000b099  sub     rax, qword ptr cs:_GUID_64ff8ccc_b287_4dae_b08a_a72cbf45f453.Data4
0x18000b0a0  test    rax, rax
0x18000b0a3  jnz     short loc_18000B0D6
0x18000b0a5  mov     [rsp+38h+var_18], rax
0x18000b0aa  mov     rax, [rcx]
0x18000b0ad  lea     r8, [rsp+38h+var_18]
0x18000b0b2  mov     rax, [rax+70h]
0x18000b0b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b0bb  mov     rax, [rsp+38h+var_18]
0x18000b0c0  mov     [rsp+38h+var_18], 0
0x18000b0c9  mov     [rbx], rax
0x18000b0cc  lea     rcx, [rsp+38h+var_18]
0x18000b0d1  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000b0d6  add     rsp, 30h
0x18000b0da  pop     rbx
0x18000b0db  retn
```
