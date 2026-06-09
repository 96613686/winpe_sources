# StructuredQuery1::NegationCondition::Save(IStream *,int)

- ea: `0x1800373d0`
- end: `0x180037529`
- name: `?Save@NegationCondition@StructuredQuery1@@UEAAJPEAUIStream@@H@Z`
- size: `345`
- prototype: `int(StructuredQuery1::NegationCondition *__hidden this, struct IStream *, int)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation`

## callees

- `0x1800373d0`
- `0x180037d50`
- `0x18005daf0`
- `0x18008b010`

## import_xrefs

- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180037421`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x1800374bf`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180037421`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x1800374bf`

## pseudocode

```c
__int64 __fastcall StructuredQuery1::NegationCondition::Save(
        StructuredQuery1::NegationCondition *this,
        struct IStream *a2)
{
  HRESULT v4; // ebx
  __int64 (__fastcall ***v5)(_QWORD, GUID *, __int64 *); // rcx
  __int64 i; // rcx
  _QWORD *v7; // rdx
  __int64 v8; // rax
  bool pv[8]; // [rsp+20h] [rbp-30h] BYREF
  __int64 v11; // [rsp+28h] [rbp-28h] BYREF
  __int128 v12; // [rsp+30h] [rbp-20h] BYREF

  if ( a2 )
  {
    v4 = StructuredQuery1::BaseCondition::Save(this, a2);
    if ( v4 >= 0 )
    {
      pv[0] = *((_QWORD *)this + 6) != 0;
      v4 = IStream_Write(a2, pv, 1u);
      if ( v4 >= 0 && pv[0] )
      {
        v5 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 6);
        v11 = 0;
        v4 = (**v5)(v5, &GUID_00000109_0000_0000_c000_000000000046, &v11);
        if ( v4 >= 0 )
        {
          v12 = 0;
          v4 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v11 + 24LL))(v11, &v12);
          if ( v4 >= 0 )
          {
            for ( i = 0; ; i = (unsigned int)(i + 1) )
            {
              if ( (unsigned int)i >= 3 )
              {
                v4 = -2147024809;
                goto LABEL_14;
              }
              v7 = (_QWORD *)*((_QWORD *)&g_rgClassIdCondition.Data1 + i);
              v8 = *v7 - v12;
              if ( *v7 == (_QWORD)v12 )
                v8 = v7[1] - *((_QWORD *)&v12 + 1);
              if ( !v8 )
                break;
            }
            v4 = IStream_Write(a2, &v12, 0x10u);
            if ( v4 >= 0 )
              v4 = (*(__int64 (__fastcall **)(__int64, struct IStream *, __int64))(*(_QWORD *)v11 + 48LL))(v11, a2, 1);
          }
LABEL_14:
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
        }
      }
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800373d0  mov     [rsp-18h+arg_10], rbx
0x1800373d5  push    rbp
0x1800373d6  push    rsi
0x1800373d7  push    rdi
0x1800373d8  mov     rbp, rsp
0x1800373db  sub     rsp, 50h
0x1800373df  mov     rax, cs:__security_cookie
0x1800373e6  xor     rax, rsp
0x1800373e9  mov     [rbp+var_10], rax
0x1800373ed  mov     rdi, rdx
0x1800373f0  mov     rsi, rcx
0x1800373f3  test    rdx, rdx
0x1800373f6  jz      loc_180037522
0x1800373fc  call    ?Save@BaseCondition@StructuredQuery1@@UEAAJPEAUIStream@@H@Z; StructuredQuery1::BaseCondition::Save(IStream *,int)
0x180037401  mov     ebx, eax
0x180037403  test    eax, eax
0x180037405  js      loc_1800374F6
0x18003740b  cmp     qword ptr [rsi+30h], 0
0x180037410  lea     rdx, [rbp+pv]; pv
0x180037414  mov     r8d, 1; cb
0x18003741a  mov     rcx, rdi; pstm
0x18003741d  setnz   [rbp+pv]
0x180037421  call    cs:__imp_IStream_Write
0x180037427  mov     ebx, eax
0x180037429  test    eax, eax
0x18003742b  js      loc_1800374F6
0x180037431  cmp     [rbp+pv], 0
0x180037435  jz      loc_1800374F6
0x18003743b  mov     rcx, [rsi+30h]
0x18003743f  lea     r8, [rbp+var_28]
0x180037443  lea     rdx, _GUID_00000109_0000_0000_c000_000000000046
0x18003744a  mov     [rbp+var_28], 0
0x180037452  mov     rax, [rcx]
0x180037455  mov     rax, [rax]
0x180037458  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003745d  mov     ebx, eax
0x18003745f  test    eax, eax
0x180037461  js      loc_1800374F6
0x180037467  mov     rcx, [rbp+var_28]
0x18003746b  lea     rdx, [rbp+var_20]
0x18003746f  xorps   xmm0, xmm0
0x180037472  movups  [rbp+var_20], xmm0
0x180037476  mov     rax, [rcx]
0x180037479  mov     rax, [rax+18h]
0x18003747d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037482  mov     ebx, eax
0x180037484  test    eax, eax
0x180037486  js      short loc_1800374E6
0x180037488  xor     ecx, ecx
0x18003748a  cmp     ecx, 3
0x18003748d  jnb     loc_18003751B
0x180037493  lea     rdx, ?g_rgClassIdCondition@@3QBQEBU_GUID@@B; _GUID const * const near * const g_rgClassIdCondition
0x18003749a  mov     rdx, [rdx+rcx*8]
0x18003749e  mov     rax, [rdx]
0x1800374a1  sub     rax, qword ptr [rbp+var_20]
0x1800374a5  jnz     short loc_1800374AF
0x1800374a7  mov     rax, [rdx+8]
0x1800374ab  sub     rax, qword ptr [rbp+var_20+8]
0x1800374af  test    rax, rax
0x1800374b2  jnz     short loc_180037514
0x1800374b4  lea     r8d, [rax+10h]; cb
0x1800374b8  mov     rcx, rdi; pstm
0x1800374bb  lea     rdx, [rbp+var_20]; pv
0x1800374bf  call    cs:__imp_IStream_Write
0x1800374c5  mov     ebx, eax
0x1800374c7  test    eax, eax
0x1800374c9  js      short loc_1800374E6
0x1800374cb  mov     rcx, [rbp+var_28]
0x1800374cf  mov     r8d, 1
0x1800374d5  mov     rdx, rdi
0x1800374d8  mov     rax, [rcx]
0x1800374db  mov     rax, [rax+30h]
0x1800374df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800374e4  mov     ebx, eax
0x1800374e6  mov     rcx, [rbp+var_28]
0x1800374ea  mov     rax, [rcx]
0x1800374ed  mov     rax, [rax+10h]
0x1800374f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800374f6  mov     eax, ebx
0x1800374f8  mov     rcx, [rbp+var_10]
0x1800374fc  xor     rcx, rsp; StackCookie
0x1800374ff  call    __security_check_cookie
0x180037504  mov     rbx, [rsp+50h+arg_10]
0x18003750c  add     rsp, 50h
0x180037510  pop     rdi
0x180037511  pop     rsi
0x180037512  pop     rbp
0x180037513  retn
0x180037514  inc     ecx
0x180037516  jmp     loc_18003748A
0x18003751b  mov     ebx, 80070057h
0x180037520  jmp     short loc_1800374E6
0x180037522  mov     ebx, 80070057h
0x180037527  jmp     short loc_1800374F6
```
