# SectionNode::GetMetadata(ConfigTreeBase *,ushort const *,tagVARIANT *)

- ea: `0x18000b5a0`
- end: `0x18000b6bf`
- name: `?GetMetadata@SectionNode@@UEAAXPEAVConfigTreeBase@@PEBGPEAUtagVARIANT@@@Z`
- size: `287`
- prototype: `void __fastcall(SectionNode *this, struct ConfigTreeBase *, wchar_t *, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x18000b3b0`
- `0x18000b5a0`
- `0x180012ea8`
- `0x180012f3c`
- `0x18001307a`
- `0x180014010`

## pseudocode

```c
void __fastcall SectionNode::GetMetadata(
        SectionNode *this,
        struct ConfigTreeBase *a2,
        wchar_t *a3,
        struct tagVARIANT *a4)
{
  __int64 v8; // rbx
  int v9; // eax
  LONGLONG v10; // rax
  _QWORD v11[5]; // [rsp+20h] [rbp-28h] BYREF
  int pExceptionObject; // [rsp+50h] [rbp+8h] BYREF

  v8 = *((_QWORD *)this + 13);
  if ( !v8 )
    goto LABEL_15;
  v11[0] = 0;
  if ( !wcscmp_0(a3, L"allowDefinition") )
  {
    v9 = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v8 + 64LL))(v8, v11);
    goto LABEL_10;
  }
  if ( !wcscmp_0(a3, L"allowLocation") )
  {
    v9 = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v8 + 80LL))(v8, v11);
    goto LABEL_10;
  }
  if ( !wcscmp_0(a3, L"overrideModeDefault") )
  {
    v9 = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v8 + 48LL))(v8, v11);
    goto LABEL_10;
  }
  if ( !wcscmp_0(a3, L"type") )
  {
    v9 = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v8 + 32LL))(v8, v11);
LABEL_10:
    if ( v9 < 0 )
    {
      pExceptionObject = v9;
      throw (long *)&pExceptionObject;
    }
    v10 = v11[0];
    if ( v11[0] )
    {
      a4->vt = 8;
      v11[0] = 0;
      a4->llVal = v10;
      ScopedBSTR::Reset((ScopedBSTR *)v11);
      return;
    }
  }
  ScopedBSTR::Reset((ScopedBSTR *)v11);
LABEL_15:
  ElementNode::GetMetadata(this, a2, a3, a4);
}

```

## disassembly

```asm
0x18000b5a0  mov     [rsp+arg_8], rbx
0x18000b5a5  mov     [rsp+arg_10], rbp
0x18000b5aa  push    rsi
0x18000b5ab  push    rdi
0x18000b5ac  push    r14
0x18000b5ae  sub     rsp, 30h
0x18000b5b2  mov     rsi, r9
0x18000b5b5  mov     rdi, r8
0x18000b5b8  mov     r14, rdx
0x18000b5bb  mov     rbp, rcx
0x18000b5be  mov     rbx, [rcx+68h]
0x18000b5c2  test    rbx, rbx
0x18000b5c5  jz      loc_18000B69B
0x18000b5cb  mov     [rsp+48h+var_28], 0
0x18000b5d4  lea     rdx, aAllowdefinitio; "allowDefinition"
0x18000b5db  mov     rcx, r8; String1
0x18000b5de  call    wcscmp_0
0x18000b5e3  test    eax, eax
0x18000b5e5  jnz     short loc_18000B5F0
0x18000b5e7  mov     rax, [rbx]
0x18000b5ea  mov     rax, [rax+40h]
0x18000b5ee  jmp     short loc_18000B642
0x18000b5f0  lea     rdx, aAllowlocation; "allowLocation"
0x18000b5f7  mov     rcx, rdi; String1
0x18000b5fa  call    wcscmp_0
0x18000b5ff  test    eax, eax
0x18000b601  jnz     short loc_18000B60C
0x18000b603  mov     rax, [rbx]
0x18000b606  mov     rax, [rax+50h]
0x18000b60a  jmp     short loc_18000B642
0x18000b60c  lea     rdx, aOverridemodede; "overrideModeDefault"
0x18000b613  mov     rcx, rdi; String1
0x18000b616  call    wcscmp_0
0x18000b61b  test    eax, eax
0x18000b61d  jnz     short loc_18000B628
0x18000b61f  mov     rax, [rbx]
0x18000b622  mov     rax, [rax+30h]
0x18000b626  jmp     short loc_18000B642
0x18000b628  lea     rdx, aType; "type"
0x18000b62f  mov     rcx, rdi; String1
0x18000b632  call    wcscmp_0
0x18000b637  test    eax, eax
0x18000b639  jnz     short loc_18000B691
0x18000b63b  mov     rax, [rbx]
0x18000b63e  mov     rax, [rax+20h]
0x18000b642  lea     rdx, [rsp+48h+var_28]
0x18000b647  mov     rcx, rbx
0x18000b64a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b64f  test    eax, eax
0x18000b651  jns     short loc_18000B669
0x18000b653  mov     [rsp+48h+pExceptionObject], eax
0x18000b657  lea     rdx, _TI1J; pThrowInfo
0x18000b65e  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18000b663  call    _CxxThrowException_0
0x18000b669  mov     rax, [rsp+48h+var_28]
0x18000b66e  test    rax, rax
0x18000b671  jz      short loc_18000B691
0x18000b673  mov     word ptr [rsi], 8
0x18000b678  mov     [rsp+48h+var_28], 0
0x18000b681  mov     [rsi+8], rax
0x18000b685  lea     rcx, [rsp+48h+var_28]; this
0x18000b68a  call    ?Reset@ScopedBSTR@@QEAAXXZ; ScopedBSTR::Reset(void)
0x18000b68f  jmp     short loc_18000B6AC
0x18000b691  lea     rcx, [rsp+48h+var_28]; this
0x18000b696  call    ?Reset@ScopedBSTR@@QEAAXXZ; ScopedBSTR::Reset(void)
0x18000b69b  mov     r9, rsi; struct tagVARIANT *
0x18000b69e  mov     r8, rdi; unsigned __int16 *
0x18000b6a1  mov     rdx, r14; struct ConfigTreeBase *
0x18000b6a4  mov     rcx, rbp; this
0x18000b6a7  call    ?GetMetadata@ElementNode@@UEAAXPEAVConfigTreeBase@@PEBGPEAUtagVARIANT@@@Z; ElementNode::GetMetadata(ConfigTreeBase *,ushort const *,tagVARIANT *)
0x18000b6ac  mov     rbx, [rsp+48h+arg_8]
0x18000b6b1  mov     rbp, [rsp+48h+arg_10]
0x18000b6b6  add     rsp, 30h
0x18000b6ba  pop     r14
0x18000b6bc  pop     rdi
0x18000b6bd  pop     rsi
0x18000b6be  retn
```
