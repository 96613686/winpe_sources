# StructuredQuery1::CConditionHistory::Load(IStream *)

- ea: `0x18003d290`
- end: `0x18003d390`
- name: `?Load@CConditionHistory@StructuredQuery1@@UEAAJPEAUIStream@@@Z`
- size: `256`
- prototype: `int(StructuredQuery1::CConditionHistory *__hidden this, struct IStream *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18003d290`
- `0x18003d398`
- `0x18003d444`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003d2a6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003d2a6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003d37f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003d37f`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18003d2b9`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18003d302`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18003d31b`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18003d334`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18003d356`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18003d2b9`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18003d302`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18003d31b`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18003d334`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18003d356`

## pseudocode

```c
__int64 __fastcall StructuredQuery1::CConditionHistory::Load(
        StructuredQuery1::CConditionHistory *this,
        struct IStream *a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbp
  HRESULT PWSTR; // ebx
  wchar_t **v6; // r8
  wchar_t **v7; // r8
  __int64 v8; // rdx
  int pv; // [rsp+50h] [rbp+8h] BYREF

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 64);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  PWSTR = IStream_Read(a2, (char *)this + 20, 4u);
  if ( PWSTR >= 0 )
  {
    PWSTR = StructuredQuery1::ReadPWSTR(a2, (StructuredQuery1::CConditionHistory *)((char *)this + 24), v6);
    if ( PWSTR >= 0 )
    {
      PWSTR = StructuredQuery1::ReadPWSTR(a2, (StructuredQuery1::CConditionHistory *)((char *)this + 32), v7);
      if ( PWSTR >= 0 )
      {
        PWSTR = IStream_Read(a2, (char *)this + 40, 4u);
        if ( PWSTR >= 0 )
        {
          PWSTR = IStream_Read(a2, (char *)this + 44, 4u);
          if ( PWSTR >= 0 )
          {
            PWSTR = IStream_Read(a2, (char *)this + 48, 8u);
            if ( PWSTR >= 0 )
            {
              pv = 0;
              PWSTR = IStream_Read(a2, &pv, 4u);
              if ( PWSTR >= 0 )
              {
                if ( pv )
                  PWSTR = LoadConditionFromStream(a2, v8, (char *)this + 56);
              }
            }
          }
        }
      }
    }
  }
  if ( v2 )
    LeaveCriticalSection(v2);
  return (unsigned int)PWSTR;
}

```

## disassembly

```asm
0x18003d290  push    rbx
0x18003d292  push    rbp
0x18003d293  push    rsi
0x18003d294  push    rdi
0x18003d295  sub     rsp, 28h
0x18003d299  lea     rbp, [rcx+40h]
0x18003d29d  mov     rsi, rcx
0x18003d2a0  mov     rcx, rbp; lpCriticalSection
0x18003d2a3  mov     rdi, rdx
0x18003d2a6  call    cs:__imp_EnterCriticalSection
0x18003d2ac  lea     rdx, [rsi+14h]; pv
0x18003d2b0  mov     r8d, 4; cb
0x18003d2b6  mov     rcx, rdi; pstm
0x18003d2b9  call    cs:__imp_IStream_Read
0x18003d2bf  mov     ebx, eax
0x18003d2c1  test    eax, eax
0x18003d2c3  js      loc_18003D377
0x18003d2c9  lea     rdx, [rsi+18h]; struct IStream *
0x18003d2cd  mov     rcx, rdi; this
0x18003d2d0  call    ?ReadPWSTR@StructuredQuery1@@YAJPEAUIStream@@PEAPEA_W@Z; StructuredQuery1::ReadPWSTR(IStream *,wchar_t * *)
0x18003d2d5  mov     ebx, eax
0x18003d2d7  test    eax, eax
0x18003d2d9  js      loc_18003D377
0x18003d2df  lea     rdx, [rsi+20h]; struct IStream *
0x18003d2e3  mov     rcx, rdi; this
0x18003d2e6  call    ?ReadPWSTR@StructuredQuery1@@YAJPEAUIStream@@PEAPEA_W@Z; StructuredQuery1::ReadPWSTR(IStream *,wchar_t * *)
0x18003d2eb  mov     ebx, eax
0x18003d2ed  test    eax, eax
0x18003d2ef  js      loc_18003D377
0x18003d2f5  lea     rdx, [rsi+28h]; pv
0x18003d2f9  mov     r8d, 4; cb
0x18003d2ff  mov     rcx, rdi; pstm
0x18003d302  call    cs:__imp_IStream_Read
0x18003d308  mov     ebx, eax
0x18003d30a  test    eax, eax
0x18003d30c  js      short loc_18003D377
0x18003d30e  lea     rdx, [rsi+2Ch]; pv
0x18003d312  mov     r8d, 4; cb
0x18003d318  mov     rcx, rdi; pstm
0x18003d31b  call    cs:__imp_IStream_Read
0x18003d321  mov     ebx, eax
0x18003d323  test    eax, eax
0x18003d325  js      short loc_18003D377
0x18003d327  lea     rdx, [rsi+30h]; pv
0x18003d32b  mov     r8d, 8; cb
0x18003d331  mov     rcx, rdi; pstm
0x18003d334  call    cs:__imp_IStream_Read
0x18003d33a  mov     ebx, eax
0x18003d33c  test    eax, eax
0x18003d33e  js      short loc_18003D377
0x18003d340  mov     r8d, 4; cb
0x18003d346  mov     [rsp+48h+pv], 0
0x18003d34e  lea     rdx, [rsp+48h+pv]; pv
0x18003d353  mov     rcx, rdi; pstm
0x18003d356  call    cs:__imp_IStream_Read
0x18003d35c  mov     ebx, eax
0x18003d35e  test    eax, eax
0x18003d360  js      short loc_18003D377
0x18003d362  cmp     [rsp+48h+pv], 0
0x18003d367  jz      short loc_18003D377
0x18003d369  lea     r8, [rsi+38h]
0x18003d36d  mov     rcx, rdi
0x18003d370  call    LoadConditionFromStream
0x18003d375  mov     ebx, eax
0x18003d377  test    rbp, rbp
0x18003d37a  jz      short loc_18003D385
0x18003d37c  mov     rcx, rbp; lpCriticalSection
0x18003d37f  call    cs:__imp_LeaveCriticalSection
0x18003d385  mov     eax, ebx
0x18003d387  add     rsp, 28h
0x18003d38b  pop     rdi
0x18003d38c  pop     rsi
0x18003d38d  pop     rbp
0x18003d38e  pop     rbx
0x18003d38f  retn
```
