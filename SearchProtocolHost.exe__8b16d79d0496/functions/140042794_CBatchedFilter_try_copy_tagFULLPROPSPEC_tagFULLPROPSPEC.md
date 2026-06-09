# CBatchedFilter::try_copy(tagFULLPROPSPEC,tagFULLPROPSPEC &)

- ea: `0x140042794`
- end: `0x14004283e`
- name: `?try_copy@CBatchedFilter@@CA_NUtagFULLPROPSPEC@@AEAU2@@Z`
- size: `170`
- prototype: `bool __fastcall(struct tagFULLPROPSPEC *__struct_ptr, struct tagFULLPROPSPEC *)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x14003fce0`
- `0x140041950`

## callees

- `0x140036570`
- `0x14003ea14`
- `0x140042794`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140042806`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140042806`

## pseudocode

```c
bool __fastcall CBatchedFilter::try_copy(struct tagFULLPROPSPEC *a1, struct tagFULLPROPSPEC *a2)
{
  ULONG ulKind; // eax
  GUID guidPropSet; // xmm6
  PROPSPEC v5; // xmm0
  bool result; // al
  PROPID propid; // rbp
  __int64 v8; // rdi
  _WORD *v9; // rsi
  PROPSPEC v10; // [rsp+30h] [rbp-48h]

  ulKind = a1->psProperty.ulKind;
  guidPropSet = a1->guidPropSet;
  v10 = 0;
  v10.ulKind = ulKind;
  if ( ulKind == 1 )
  {
    LODWORD(v10.propid) = a1->psProperty.propid;
  }
  else if ( !ulKind )
  {
    propid = a1->psProperty.propid;
    if ( propid )
    {
      v8 = std::_WChar_traits<wchar_t>::length(a1->psProperty.propid);
      v9 = CoTaskMemAlloc(2 * v8 + 2);
      if ( !v9 )
      {
        v5 = 0;
        result = 0;
        a2->guidPropSet = 0;
        goto LABEL_4;
      }
      if ( v8 )
        std::_Copy_memmove_n<wchar_t const *,wchar_t *>(propid);
      v10.propid = v9;
      v9[v8] = 0;
    }
    else
    {
      v10.propid = 0;
    }
  }
  v5 = v10;
  result = 1;
  a2->guidPropSet = guidPropSet;
LABEL_4:
  a2->psProperty = v5;
  return result;
}

```

## disassembly

```asm
0x140042794  push    rbx
0x140042796  push    rbp
0x140042797  push    rsi
0x140042798  push    rdi
0x140042799  sub     rsp, 58h
0x14004279d  mov     eax, [rcx+10h]
0x1400427a0  xorps   xmm0, xmm0
0x1400427a3  movaps  [rsp+78h+var_38], xmm6
0x1400427a8  mov     rbx, rdx
0x1400427ab  movups  xmm6, xmmword ptr [rcx]
0x1400427ae  movups  [rsp+78h+var_48], xmm0
0x1400427b3  mov     dword ptr [rsp+78h+var_48], eax
0x1400427b7  cmp     eax, 1
0x1400427ba  jnz     short loc_1400427DF
0x1400427bc  mov     eax, [rcx+18h]
0x1400427bf  mov     dword ptr [rsp+78h+var_48+8], eax
0x1400427c3  movups  xmm0, [rsp+78h+var_48]
0x1400427c8  mov     al, 1
0x1400427ca  movups  xmmword ptr [rbx], xmm6
0x1400427cd  movaps  xmm6, [rsp+78h+var_38]
0x1400427d2  movups  xmmword ptr [rbx+10h], xmm0
0x1400427d6  add     rsp, 58h
0x1400427da  pop     rdi
0x1400427db  pop     rsi
0x1400427dc  pop     rbp
0x1400427dd  pop     rbx
0x1400427de  retn
0x1400427df  test    eax, eax
0x1400427e1  jnz     short loc_1400427C3
0x1400427e3  mov     rbp, [rcx+18h]
0x1400427e7  test    rbp, rbp
0x1400427ea  jnz     short loc_1400427F3
0x1400427ec  mov     qword ptr [rsp+78h+var_48+8], rbp
0x1400427f1  jmp     short loc_1400427C3
0x1400427f3  mov     rcx, rbp
0x1400427f6  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x1400427fb  mov     rdi, rax
0x1400427fe  lea     rcx, ds:2[rax*2]; cb
0x140042806  call    cs:__imp_CoTaskMemAlloc
0x14004280c  mov     rsi, rax
0x14004280f  test    rax, rax
0x140042812  jz      short loc_140042834
0x140042814  test    rdi, rdi
0x140042817  jz      short loc_140042827
0x140042819  mov     r8, rax
0x14004281c  mov     rdx, rdi
0x14004281f  mov     rcx, rbp; Src
0x140042822  call    ??$_Copy_memmove_n@PEB_WPEA_W@std@@YAPEA_WPEB_W_KPEA_W@Z; std::_Copy_memmove_n<wchar_t const *,wchar_t *>(wchar_t const *,unsigned __int64,wchar_t *)
0x140042827  xor     eax, eax
0x140042829  mov     qword ptr [rsp+78h+var_48+8], rsi
0x14004282e  mov     [rsi+rdi*2], ax
0x140042832  jmp     short loc_1400427C3
0x140042834  xorps   xmm0, xmm0
0x140042837  xor     al, al
0x140042839  movups  xmmword ptr [rbx], xmm0
0x14004283c  jmp     short loc_1400427CD
```
