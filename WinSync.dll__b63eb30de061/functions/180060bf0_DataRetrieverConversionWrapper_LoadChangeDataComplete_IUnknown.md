# DataRetrieverConversionWrapper::LoadChangeDataComplete(IUnknown *)

- ea: `0x180060bf0`
- end: `0x180060d34`
- name: `?LoadChangeDataComplete@DataRetrieverConversionWrapper@@UEAAJPEAUIUnknown@@@Z`
- size: `324`
- prototype: `int(DataRetrieverConversionWrapper *__hidden this, struct IUnknown *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x18001a038`
- `0x18001ae20`
- `0x180060800`
- `0x180060bf0`
- `0x180094010`

## string_xrefs

- `0x180060c2c`: `DataRetrieverConversionWrapper::LoadChangeDataComplete`
- `0x180060d02`: `DataRetrieverConversionWrapper::LoadChangeDataComplete`

## pseudocode

```c
__int64 __fastcall DataRetrieverConversionWrapper::LoadChangeDataComplete(
        DataRetrieverConversionWrapper *this,
        struct IUnknown *a2)
{
  struct ILoadChangeContext *v4; // rdx
  __int64 **v5; // rbx
  int v6; // esi
  __int64 v7; // rcx
  __int64 *v8; // rcx
  __int64 v9; // rax
  unsigned int v10; // eax
  unsigned int v11; // ebx
  struct IUnknown *v13; // [rsp+50h] [rbp+8h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      28,
      WPP_718d8ca8bd2838e4eed2fae745717fa6_Traceguids,
      "DataRetrieverConversionWrapper::LoadChangeDataComplete");
  }
  v13 = 0;
  v4 = (struct ILoadChangeContext *)*((_QWORD *)this + 7);
  v5 = (__int64 **)((char *)this + 48);
  if ( v4 && *v5 )
    v6 = DataRetrieverConversionWrapper::ConvertData(
           (DataRetrieverConversionWrapper *)((char *)this - 16),
           v4,
           a2,
           &v13);
  else
    v6 = -2147217407;
  v7 = *((_QWORD *)this + 7);
  if ( v7 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    *((_QWORD *)this + 7) = 0;
  }
  v8 = *v5;
  v9 = **v5;
  if ( v6 < 0 )
    v10 = (*(__int64 (__fastcall **)(__int64 *, _QWORD))(v9 + 32))(v8, (unsigned int)v6);
  else
    v10 = (*(__int64 (__fastcall **)(__int64 *, struct IUnknown *))(v9 + 24))(v8, v13);
  v11 = v10;
  if ( v13 )
    ((void (__fastcall *)(struct IUnknown *))v13->lpVtbl->Release)(v13);
  (*(void (__fastcall **)(char *))(*((_QWORD *)this - 2) + 16LL))((char *)this - 16);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      29,
      (unsigned int)WPP_718d8ca8bd2838e4eed2fae745717fa6_Traceguids,
      (unsigned int)"DataRetrieverConversionWrapper::LoadChangeDataComplete",
      v11);
  }
  return v11;
}

```

## disassembly

```asm
0x180060bf0  mov     [rsp+arg_8], rbx
0x180060bf5  mov     [rsp+arg_10], rsi
0x180060bfa  push    rdi
0x180060bfb  push    r14
0x180060bfd  push    r15
0x180060bff  sub     rsp, 30h
0x180060c03  mov     rsi, rdx
0x180060c06  mov     rdi, rcx
0x180060c09  mov     rcx, cs:WPP_GLOBAL_Control
0x180060c10  lea     r15, WPP_GLOBAL_Control
0x180060c17  cmp     rcx, r15
0x180060c1a  jz      short loc_180060C44
0x180060c1c  test    byte ptr [rcx+1Ch], 4
0x180060c20  jz      short loc_180060C44
0x180060c22  cmp     byte ptr [rcx+19h], 5
0x180060c26  jb      short loc_180060C44
0x180060c28  mov     rcx, [rcx+10h]
0x180060c2c  lea     r9, aDataretrieverc_9; "DataRetrieverConversionWrapper::LoadCha"...
0x180060c33  mov     edx, 1Ch
0x180060c38  lea     r8, WPP_718d8ca8bd2838e4eed2fae745717fa6_Traceguids
0x180060c3f  call    WPP_SF_s
0x180060c44  lea     r14, [rdi-10h]
0x180060c48  mov     [rsp+48h+arg_0], 0
0x180060c51  mov     rdx, [r14+48h]; struct ILoadChangeContext *
0x180060c55  lea     rbx, [rdi+30h]
0x180060c59  test    rdx, rdx
0x180060c5c  jz      short loc_180060C78
0x180060c5e  cmp     qword ptr [rbx], 0
0x180060c62  jz      short loc_180060C78
0x180060c64  lea     r9, [rsp+48h+arg_0]; struct IUnknown **
0x180060c69  mov     r8, rsi; struct IUnknown *
0x180060c6c  mov     rcx, r14; this
0x180060c6f  call    ?ConvertData@DataRetrieverConversionWrapper@@AEAAJPEAUILoadChangeContext@@PEAUIUnknown@@PEAPEAU3@@Z; DataRetrieverConversionWrapper::ConvertData(ILoadChangeContext *,IUnknown *,IUnknown * *)
0x180060c74  mov     esi, eax
0x180060c76  jmp     short loc_180060C7D
0x180060c78  mov     esi, 80041001h
0x180060c7d  mov     rcx, [rdi+38h]
0x180060c81  test    rcx, rcx
0x180060c84  jz      short loc_180060C9A
0x180060c86  mov     rax, [rcx]
0x180060c89  mov     rax, [rax+10h]
0x180060c8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060c92  mov     qword ptr [rdi+38h], 0
0x180060c9a  mov     rcx, [rbx]
0x180060c9d  mov     rax, [rcx]
0x180060ca0  test    esi, esi
0x180060ca2  js      short loc_180060CB4
0x180060ca4  mov     rdx, [rsp+48h+arg_0]
0x180060ca9  mov     rax, [rax+18h]
0x180060cad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060cb2  jmp     short loc_180060CBF
0x180060cb4  mov     rax, [rax+20h]
0x180060cb8  mov     edx, esi
0x180060cba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060cbf  mov     rcx, [rsp+48h+arg_0]
0x180060cc4  mov     ebx, eax
0x180060cc6  test    rcx, rcx
0x180060cc9  jz      short loc_180060CD7
0x180060ccb  mov     rax, [rcx]
0x180060cce  mov     rax, [rax+10h]
0x180060cd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060cd7  mov     rax, [r14]
0x180060cda  mov     rcx, r14
0x180060cdd  mov     rax, [rax+10h]
0x180060ce1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060ce6  mov     rcx, cs:WPP_GLOBAL_Control
0x180060ced  cmp     rcx, r15
0x180060cf0  jz      short loc_180060D1E
0x180060cf2  test    byte ptr [rcx+1Ch], 4
0x180060cf6  jz      short loc_180060D1E
0x180060cf8  cmp     byte ptr [rcx+19h], 5
0x180060cfc  jb      short loc_180060D1E
0x180060cfe  mov     rcx, [rcx+10h]
0x180060d02  lea     r9, aDataretrieverc_9; "DataRetrieverConversionWrapper::LoadCha"...
0x180060d09  mov     edx, 1Dh
0x180060d0e  mov     [rsp+48h+var_28], ebx
0x180060d12  lea     r8, WPP_718d8ca8bd2838e4eed2fae745717fa6_Traceguids
0x180060d19  call    WPP_SF_sD
0x180060d1e  mov     rsi, [rsp+48h+arg_10]
0x180060d23  mov     eax, ebx
0x180060d25  mov     rbx, [rsp+48h+arg_8]
0x180060d2a  add     rsp, 30h
0x180060d2e  pop     r15
0x180060d30  pop     r14
0x180060d32  pop     rdi
0x180060d33  retn
```
