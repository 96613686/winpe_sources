# StructuredQuery1::BaseCondition::Save(IStream *,int)

- ea: `0x180037d50`
- end: `0x180037e42`
- name: `?Save@BaseCondition@StructuredQuery1@@UEAAJPEAUIStream@@H@Z`
- size: `242`
- prototype: `int(StructuredQuery1::BaseCondition *__hidden this, struct IStream *, int)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x1800373d0`
- `0x180037530`
- `0x180037740`

## callees

- `0x180037d50`
- `0x18003bf00`
- `0x18006749c`

## import_xrefs

- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180037d9f`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180037de1`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180037d9f`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180037de1`

## pseudocode

```c
HRESULT __fastcall StructuredQuery1::BaseCondition::Save(StructuredQuery1::BaseCondition *this, struct IStream *a2)
{
  __int64 v4; // rax
  int i; // r8d
  HRESULT result; // eax
  _QWORD *j; // rbx
  int pv; // [rsp+38h] [rbp+10h] BYREF

  if ( !a2 )
    return -2147024809;
  v4 = *((_QWORD *)this + 5);
  for ( i = 0; v4; ++i )
    v4 = *(_QWORD *)(v4 + 24);
  pv = i;
  result = IStream_Write(a2, &pv, 4u);
  if ( result >= 0 )
  {
    for ( j = (_QWORD *)*((_QWORD *)this + 5); j; j = (_QWORD *)j[3] )
    {
      result = IStream_Write(a2, j, 0x10u);
      if ( result < 0 )
        break;
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_FI45262758>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_FI45262758>::GetImpl'::`2'::impl);
      result = SQ_IUnknown_SaveKnownImplToStream(a2);
      if ( result < 0 )
        break;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180037d50  mov     [rsp+arg_18], rbx
0x180037d55  push    rdi
0x180037d56  sub     rsp, 20h
0x180037d5a  mov     rdi, rdx
0x180037d5d  mov     rbx, rcx
0x180037d60  test    rdx, rdx
0x180037d63  jz      loc_180037E1D
0x180037d69  mov     rax, [rcx+28h]
0x180037d6d  xor     r8d, r8d
0x180037d70  test    rax, rax
0x180037d73  jz      short loc_180037D8C
0x180037d75  nop     word ptr [rax+rax+00000000h]
0x180037d80  mov     rax, [rax+18h]
0x180037d84  inc     r8d
0x180037d87  test    rax, rax
0x180037d8a  jnz     short loc_180037D80
0x180037d8c  mov     [rsp+28h+pv], r8d
0x180037d91  lea     rdx, [rsp+28h+pv]; pv
0x180037d96  mov     r8d, 4; cb
0x180037d9c  mov     rcx, rdi; pstm
0x180037d9f  call    cs:__imp_IStream_Write
0x180037da5  test    eax, eax
0x180037da7  js      loc_180037E37
0x180037dad  mov     rbx, [rbx+28h]
0x180037db1  mov     [rsp+28h+arg_0], rbp
0x180037db6  lea     rbp, ?g_oldRgClassIdAttribute@@3QBQEBU_GUID@@B; _GUID const * const near * const g_oldRgClassIdAttribute
0x180037dbd  mov     [rsp+28h+arg_10], rsi
0x180037dc2  lea     rsi, ?g_rgClassIdAttribute@@3QBQEBU_GUID@@B; _GUID const * const near * const g_rgClassIdAttribute
0x180037dc9  nop     dword ptr [rax+00000000h]
0x180037dd0  test    rbx, rbx
0x180037dd3  jz      short loc_180037E2D
0x180037dd5  mov     r8d, 10h; cb
0x180037ddb  mov     rdx, rbx; pv
0x180037dde  mov     rcx, rdi; pstm
0x180037de1  call    cs:__imp_IStream_Write
0x180037de7  test    eax, eax
0x180037de9  js      short loc_180037E2D
0x180037deb  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_FI45262758@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_FI45262758@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FI45262758> `wil::Feature<__WilFeatureTraits_Feature_FI45262758>::GetImpl(void)'::`2'::impl
0x180037df2  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_FI45262758@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FI45262758>::__private_IsEnabled(void)
0x180037df7  mov     r9, [rbx+10h]
0x180037dfb  mov     rdx, rsi
0x180037dfe  movzx   eax, al
0x180037e01  mov     rcx, rdi; pstm
0x180037e04  test    al, al
0x180037e06  cmovz   rdx, rbp
0x180037e0a  lea     r8d, [rax+2]
0x180037e0e  call    SQ_IUnknown_SaveKnownImplToStream
0x180037e13  test    eax, eax
0x180037e15  js      short loc_180037E2D
0x180037e17  mov     rbx, [rbx+18h]
0x180037e1b  jmp     short loc_180037DD0
0x180037e1d  mov     eax, 80070057h
0x180037e22  mov     rbx, [rsp+28h+arg_18]
0x180037e27  add     rsp, 20h
0x180037e2b  pop     rdi
0x180037e2c  retn
0x180037e2d  mov     rbp, [rsp+28h+arg_0]
0x180037e32  mov     rsi, [rsp+28h+arg_10]
0x180037e37  mov     rbx, [rsp+28h+arg_18]
0x180037e3c  add     rsp, 20h
0x180037e40  pop     rdi
0x180037e41  retn
```
