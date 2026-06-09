# StructuredQuery1::CConditionHistory::Save(IStream *,int)

- ea: `0x18003e890`
- end: `0x18003eb2e`
- name: `?Save@CConditionHistory@StructuredQuery1@@UEAAJPEAUIStream@@H@Z`
- size: `670`
- prototype: `int(StructuredQuery1::CConditionHistory *__hidden this, struct IStream *, int)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation`

## callees

- `0x18003e890`
- `0x18005daf0`
- `0x18008b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003e8c2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003e8c2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003e924`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003e924`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x18003e8d5`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x18003e910`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x18003e96c`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x18003e9a6`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x18003e9cd`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x18003e9e7`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x18003ea01`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x18003ea1e`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x18003ea45`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x18003eaeb`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x18003e8d5`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x18003e910`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x18003e96c`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x18003e9a6`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x18003e9cd`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x18003e9e7`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x18003ea01`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x18003ea1e`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x18003ea45`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x18003eaeb`

## pseudocode

```c
__int64 __fastcall StructuredQuery1::CConditionHistory::Save(
        StructuredQuery1::CConditionHistory *this,
        struct IStream *a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbx
  HRESULT v5; // edi
  _WORD *v6; // r12
  __int64 v7; // r15
  __int64 v8; // rax
  int v9; // eax
  _WORD *v11; // r12
  int v12; // r15d
  __int64 (__fastcall ***v13)(_QWORD, GUID *, __int64 *); // rcx
  __int64 (__fastcall **v14)(_QWORD, GUID *, __int64 *); // rax
  unsigned int i; // ecx
  _QWORD *v16; // rdx
  __int64 v17; // rax
  BOOL pv; // [rsp+20h] [rbp-30h] BYREF
  __int64 v19; // [rsp+28h] [rbp-28h] BYREF
  __int128 v20; // [rsp+30h] [rbp-20h] BYREF

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 64);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  v5 = IStream_Write(a2, (char *)this + 20, 4u);
  if ( v5 >= 0 )
  {
    v6 = (_WORD *)*((_QWORD *)this + 3);
    v7 = -1;
    if ( v6 )
    {
      v8 = -1;
      do
        ++v8;
      while ( v6[v8] );
      v9 = v8 + 1;
    }
    else
    {
      v9 = 0;
    }
    pv = v9;
    v5 = IStream_Write(a2, &pv, 4u);
    if ( v5 >= 0 )
    {
      if ( !pv || (v5 = IStream_Write(a2, v6, 2 * pv - 2), v5 >= 0) )
      {
        v11 = (_WORD *)*((_QWORD *)this + 4);
        if ( v11 )
        {
          do
            ++v7;
          while ( v11[v7] );
          v12 = v7 + 1;
        }
        else
        {
          v12 = 0;
        }
        pv = v12;
        v5 = IStream_Write(a2, &pv, 4u);
        if ( v5 >= 0 )
        {
          if ( !pv || (v5 = IStream_Write(a2, v11, 2 * pv - 2), v5 >= 0) )
          {
            v5 = IStream_Write(a2, (char *)this + 40, 4u);
            if ( v5 >= 0 )
            {
              v5 = IStream_Write(a2, (char *)this + 44, 4u);
              if ( v5 >= 0 )
              {
                v5 = IStream_Write(a2, (char *)this + 48, 8u);
                if ( v5 >= 0 )
                {
                  pv = *((_QWORD *)this + 7) != 0;
                  v5 = IStream_Write(a2, &pv, 4u);
                  if ( v5 >= 0 )
                  {
                    v13 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 7);
                    if ( v13 )
                    {
                      v14 = *v13;
                      v19 = 0;
                      v5 = (*v14)(v13, &GUID_00000109_0000_0000_c000_000000000046, &v19);
                      if ( v5 >= 0 )
                      {
                        v20 = 0;
                        v5 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v19 + 24LL))(v19, &v20);
                        if ( v5 >= 0 )
                        {
                          for ( i = 0; ; ++i )
                          {
                            if ( i >= 3 )
                            {
                              v5 = -2147024809;
                              goto LABEL_35;
                            }
                            v16 = (_QWORD *)*((_QWORD *)&g_rgClassIdCondition.Data1 + i);
                            v17 = *v16 - v20;
                            if ( *v16 == (_QWORD)v20 )
                              v17 = v16[1] - *((_QWORD *)&v20 + 1);
                            if ( !v17 )
                              break;
                          }
                          v5 = IStream_Write(a2, &v20, 0x10u);
                          if ( v5 >= 0 )
                            v5 = (*(__int64 (__fastcall **)(__int64, struct IStream *, __int64))(*(_QWORD *)v19 + 48LL))(
                                   v19,
                                   a2,
                                   1);
                        }
LABEL_35:
                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  if ( v2 )
    LeaveCriticalSection(v2);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18003e890  mov     [rsp-38h+arg_10], rbx
0x18003e895  push    rbp
0x18003e896  push    rsi
0x18003e897  push    rdi
0x18003e898  push    r12
0x18003e89a  push    r13
0x18003e89c  push    r14
0x18003e89e  push    r15
0x18003e8a0  mov     rbp, rsp
0x18003e8a3  sub     rsp, 50h
0x18003e8a7  mov     rax, cs:__security_cookie
0x18003e8ae  xor     rax, rsp
0x18003e8b1  mov     [rbp+var_10], rax
0x18003e8b5  lea     rbx, [rcx+40h]
0x18003e8b9  mov     rsi, rcx
0x18003e8bc  mov     rcx, rbx; lpCriticalSection
0x18003e8bf  mov     r14, rdx
0x18003e8c2  call    cs:__imp_EnterCriticalSection
0x18003e8c8  lea     rdx, [rsi+14h]; pv
0x18003e8cc  mov     r8d, 4; cb
0x18003e8d2  mov     rcx, r14; pstm
0x18003e8d5  call    cs:__imp_IStream_Write
0x18003e8db  xor     r13d, r13d
0x18003e8de  mov     edi, eax
0x18003e8e0  test    eax, eax
0x18003e8e2  js      short loc_18003E91C
0x18003e8e4  mov     r12, [rsi+18h]
0x18003e8e8  or      r15, 0FFFFFFFFFFFFFFFFh
0x18003e8ec  test    r12, r12
0x18003e8ef  jz      short loc_18003E950
0x18003e8f1  mov     rax, r15
0x18003e8f4  inc     rax
0x18003e8f7  cmp     [r12+rax*2], r13w
0x18003e8fc  jnz     short loc_18003E8F4
0x18003e8fe  inc     eax
0x18003e900  mov     r8d, 4; cb
0x18003e906  mov     [rbp+pv], eax
0x18003e909  lea     rdx, [rbp+pv]; pv
0x18003e90d  mov     rcx, r14; pstm
0x18003e910  call    cs:__imp_IStream_Write
0x18003e916  mov     edi, eax
0x18003e918  test    eax, eax
0x18003e91a  jns     short loc_18003E955
0x18003e91c  test    rbx, rbx
0x18003e91f  jz      short loc_18003E92A
0x18003e921  mov     rcx, rbx; lpCriticalSection
0x18003e924  call    cs:__imp_LeaveCriticalSection
0x18003e92a  mov     eax, edi
0x18003e92c  mov     rcx, [rbp+var_10]
0x18003e930  xor     rcx, rsp; StackCookie
0x18003e933  call    __security_check_cookie
0x18003e938  mov     rbx, [rsp+50h+arg_10]
0x18003e940  add     rsp, 50h
0x18003e944  pop     r15
0x18003e946  pop     r14
0x18003e948  pop     r13
0x18003e94a  pop     r12
0x18003e94c  pop     rdi
0x18003e94d  pop     rsi
0x18003e94e  pop     rbp
0x18003e94f  retn
0x18003e950  mov     eax, r13d
0x18003e953  jmp     short loc_18003E900
0x18003e955  mov     r8d, [rbp+pv]
0x18003e959  test    r8d, r8d
0x18003e95c  jz      short loc_18003E978
0x18003e95e  lea     r8d, ds:0FFFFFFFFFFFFFFFEh[r8*2]; cb
0x18003e966  mov     rdx, r12; pv
0x18003e969  mov     rcx, r14; pstm
0x18003e96c  call    cs:__imp_IStream_Write
0x18003e972  mov     edi, eax
0x18003e974  test    eax, eax
0x18003e976  js      short loc_18003E91C
0x18003e978  mov     r12, [rsi+20h]
0x18003e97c  test    r12, r12
0x18003e97f  jz      loc_18003EAD6
0x18003e985  inc     r15
0x18003e988  cmp     [r12+r15*2], r13w
0x18003e98d  jnz     short loc_18003E985
0x18003e98f  inc     r15d
0x18003e992  mov     [rbp+pv], r15d
0x18003e996  lea     rdx, [rbp+pv]; pv
0x18003e99a  mov     r15d, 4
0x18003e9a0  mov     rcx, r14; pstm
0x18003e9a3  mov     r8d, r15d; cb
0x18003e9a6  call    cs:__imp_IStream_Write
0x18003e9ac  mov     edi, eax
0x18003e9ae  test    eax, eax
0x18003e9b0  js      loc_18003E91C
0x18003e9b6  mov     r8d, [rbp+pv]
0x18003e9ba  test    r8d, r8d
0x18003e9bd  jz      short loc_18003E9DD
0x18003e9bf  lea     r8d, ds:0FFFFFFFFFFFFFFFEh[r8*2]; cb
0x18003e9c7  mov     rdx, r12; pv
0x18003e9ca  mov     rcx, r14; pstm
0x18003e9cd  call    cs:__imp_IStream_Write
0x18003e9d3  mov     edi, eax
0x18003e9d5  test    eax, eax
0x18003e9d7  js      loc_18003E91C
0x18003e9dd  lea     rdx, [rsi+28h]; pv
0x18003e9e1  mov     r8d, r15d; cb
0x18003e9e4  mov     rcx, r14; pstm
0x18003e9e7  call    cs:__imp_IStream_Write
0x18003e9ed  mov     edi, eax
0x18003e9ef  test    eax, eax
0x18003e9f1  js      loc_18003E91C
0x18003e9f7  lea     rdx, [rsi+2Ch]; pv
0x18003e9fb  mov     r8d, r15d; cb
0x18003e9fe  mov     rcx, r14; pstm
0x18003ea01  call    cs:__imp_IStream_Write
0x18003ea07  mov     edi, eax
0x18003ea09  test    eax, eax
0x18003ea0b  js      loc_18003E91C
0x18003ea11  lea     rdx, [rsi+30h]; pv
0x18003ea15  mov     r8d, 8; cb
0x18003ea1b  mov     rcx, r14; pstm
0x18003ea1e  call    cs:__imp_IStream_Write
0x18003ea24  mov     edi, eax
0x18003ea26  test    eax, eax
0x18003ea28  js      loc_18003E91C
0x18003ea2e  cmp     [rsi+38h], r13
0x18003ea32  lea     rdx, [rbp+pv]; pv
0x18003ea36  mov     eax, r13d
0x18003ea39  mov     r8d, r15d; cb
0x18003ea3c  setnz   al
0x18003ea3f  mov     rcx, r14; pstm
0x18003ea42  mov     [rbp+pv], eax
0x18003ea45  call    cs:__imp_IStream_Write
0x18003ea4b  mov     edi, eax
0x18003ea4d  test    eax, eax
0x18003ea4f  js      loc_18003E91C
0x18003ea55  mov     rcx, [rsi+38h]
0x18003ea59  test    rcx, rcx
0x18003ea5c  jz      loc_18003E91C
0x18003ea62  mov     rax, [rcx]
0x18003ea65  lea     r8, [rbp+var_28]
0x18003ea69  lea     rdx, _GUID_00000109_0000_0000_c000_000000000046
0x18003ea70  mov     [rbp+var_28], r13
0x18003ea74  mov     rax, [rax]
0x18003ea77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ea7c  mov     edi, eax
0x18003ea7e  test    eax, eax
0x18003ea80  js      loc_18003E91C
0x18003ea86  mov     rcx, [rbp+var_28]
0x18003ea8a  lea     rdx, [rbp+var_20]
0x18003ea8e  xorps   xmm0, xmm0
0x18003ea91  movups  [rbp+var_20], xmm0
0x18003ea95  mov     rax, [rcx]
0x18003ea98  mov     rax, [rax+18h]
0x18003ea9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003eaa1  mov     edi, eax
0x18003eaa3  test    eax, eax
0x18003eaa5  js      short loc_18003EB12
0x18003eaa7  mov     ecx, r13d
0x18003eaaa  cmp     ecx, 3
0x18003eaad  jnb     short loc_18003EB27
0x18003eaaf  mov     eax, ecx
0x18003eab1  lea     rdx, ?g_rgClassIdCondition@@3QBQEBU_GUID@@B; _GUID const * const near * const g_rgClassIdCondition
0x18003eab8  mov     rdx, [rdx+rax*8]
0x18003eabc  mov     rax, [rdx]
0x18003eabf  sub     rax, qword ptr [rbp+var_20]
0x18003eac3  jnz     short loc_18003EACD
0x18003eac5  mov     rax, [rdx+8]
0x18003eac9  sub     rax, qword ptr [rbp+var_20+8]
0x18003eacd  test    rax, rax
0x18003ead0  jz      short loc_18003EADE
0x18003ead2  inc     ecx
0x18003ead4  jmp     short loc_18003EAAA
0x18003ead6  mov     r15d, r13d
0x18003ead9  jmp     loc_18003E992
0x18003eade  mov     r8d, 10h; cb
0x18003eae4  lea     rdx, [rbp+var_20]; pv
0x18003eae8  mov     rcx, r14; pstm
0x18003eaeb  call    cs:__imp_IStream_Write
0x18003eaf1  mov     edi, eax
0x18003eaf3  test    eax, eax
0x18003eaf5  js      short loc_18003EB12
0x18003eaf7  mov     rcx, [rbp+var_28]
0x18003eafb  mov     r8d, 1
0x18003eb01  mov     rdx, r14
0x18003eb04  mov     rax, [rcx]
0x18003eb07  mov     rax, [rax+30h]
0x18003eb0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003eb10  mov     edi, eax
0x18003eb12  mov     rcx, [rbp+var_28]
0x18003eb16  mov     rax, [rcx]
0x18003eb19  mov     rax, [rax+10h]
0x18003eb1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003eb22  jmp     loc_18003E91C
0x18003eb27  mov     edi, 80070057h
0x18003eb2c  jmp     short loc_18003EB12
```
