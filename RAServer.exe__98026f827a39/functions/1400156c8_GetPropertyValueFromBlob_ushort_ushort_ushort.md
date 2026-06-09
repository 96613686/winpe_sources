# GetPropertyValueFromBlob(ushort *,ushort *,ushort * *)

- ea: `0x1400156c8`
- end: `0x1400158d8`
- name: `?GetPropertyValueFromBlob@@YAHPEAG0PEAPEAG@Z`
- size: `528`
- prototype: `__int64 __fastcall(wchar_t *String, const struct _EVENT_DESCRIPTOR *String2, unsigned __int16 **)`
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140013c10`
- `0x140014740`
- `0x140014894`

## callees

- `0x140015240`
- `0x1400156c8`
- `0x1400158e0`
- `0x140015a6e`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x140015843`
- `KERNEL32!HeapAlloc` at `0x140015843`
- `KERNEL32!GetProcessHeap` at `0x140015832`
- `KERNEL32!GetProcessHeap` at `0x140015832`
- `msvcrt!_wtol` at `0x1400157a5`
- `msvcrt!_wtol` at `0x1400157a5`
- `msvcrt!iswdigit` at `0x14001577a`
- `msvcrt!iswdigit` at `0x14001577a`

## string_xrefs

- `0x1400158b3`: `base\diagnosis\ra\racommon\src\stringutils.cpp`

## pseudocode

```c
__int64 __fastcall GetPropertyValueFromBlob(
        wchar_t *String,
        const struct _EVENT_DESCRIPTOR *String2,
        unsigned __int16 **a3)
{
  wint_t *v5; // rbx
  unsigned int v6; // r12d
  wint_t v7; // ax
  unsigned __int64 v8; // rsi
  __int64 v9; // rcx
  wint_t *v10; // r13
  const wchar_t *v11; // rdi
  unsigned __int64 v12; // rdi
  unsigned __int64 v13; // rbx
  const wchar_t *v14; // r14
  __int16 v15; // ax
  unsigned __int64 v16; // rdi
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v18; // rax
  const struct _EVENT_DESCRIPTOR *v19; // rdx
  CEventLogger *v20; // rcx
  signed int v21; // eax
  const struct _EVENT_DESCRIPTOR *v22; // rdx
  CEventLogger *v23; // rcx
  unsigned int v24; // r9d

  v5 = String;
  v6 = 0;
  if ( String )
  {
    if ( String2 )
    {
      if ( a3 )
      {
        v7 = *String;
        if ( *String && String2->Id )
        {
          v8 = -1;
          v9 = -1;
          do
            ++v9;
          while ( v5[v9] );
          v10 = &v5[v9];
          v11 = v5;
          do
            ++v8;
          while ( *(&String2->Id + v8) );
          while ( 1 )
          {
            if ( v7 != 59 )
            {
              do
              {
                if ( !v7 )
                  break;
                if ( !iswdigit(v7) )
                  break;
                v7 = *++v5;
              }
              while ( *v5 != 59 );
              if ( *v5 != 59 )
                break;
            }
            *v5 = 0;
            v12 = _wtol(v11);
            *v5 = 59;
            if ( v12 <= v8 )
            {
              v24 = 751;
              goto LABEL_35;
            }
            v13 = (unsigned __int64)(v5 + 1);
            v14 = (const wchar_t *)v13;
            v15 = *(_WORD *)v13;
            if ( *(_WORD *)v13 != 61 )
            {
              do
              {
                if ( !v15 )
                  break;
                if ( v13 >= (unsigned __int64)&v14[v12] )
                  break;
                v13 += 2LL;
                v15 = *(_WORD *)v13;
              }
              while ( *(_WORD *)v13 != 61 );
              if ( *(_WORD *)v13 != 61 )
                return v6;
            }
            if ( !wcsncmp_0(v14, &String2->Id, (unsigned int)v8) )
            {
              if ( v12 != v8 + 1 )
              {
                v16 = v12 - v8;
                ProcessHeap = GetProcessHeap();
                v18 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 8u, 2 * v16);
                *a3 = v18;
                if ( v18 )
                {
                  v21 = StringCchCopyNW(v18, v16, (const unsigned __int16 *)(v13 + 2), v16 - 1);
                  if ( v21 >= 0 )
                  {
                    v6 = 1;
                    (*a3)[v16 - 1] = 0;
                  }
                  else
                  {
                    CEventLogger::LogError(
                      v23,
                      v22,
                      L"base\\diagnosis\\ra\\racommon\\src\\stringutils.cpp",
                      0x30Fu,
                      L"GetPropertyValueFromBlob",
                      v21);
                  }
                }
                else
                {
                  CEventLogger::LogError(
                    v20,
                    v19,
                    L"base\\diagnosis\\ra\\racommon\\src\\stringutils.cpp",
                    0x30Au,
                    L"GetPropertyValueFromBlob",
                    0x8007000E);
                }
              }
              return v6;
            }
            v11 = &v14[v12];
            if ( v11 > v10 )
              return v6;
            v7 = *v11;
            v5 = (wint_t *)v11;
          }
        }
        else
        {
          v24 = 719;
LABEL_35:
          CEventLogger::LogError(
            (CEventLogger *)String,
            String2,
            L"base\\diagnosis\\ra\\racommon\\src\\stringutils.cpp",
            v24,
            L"GetPropertyValueFromBlob",
            0x80070057);
        }
      }
      else
      {
        CEventLogger::LogError(
          (CEventLogger *)String,
          String2,
          L"base\\diagnosis\\ra\\racommon\\src\\stringutils.cpp",
          0x2CAu,
          L"GetPropertyValueFromBlob",
          0x80004003);
      }
    }
    else
    {
      CEventLogger::LogError(
        (CEventLogger *)String,
        0,
        L"base\\diagnosis\\ra\\racommon\\src\\stringutils.cpp",
        0x2C9u,
        L"GetPropertyValueFromBlob",
        0x80004003);
    }
  }
  else
  {
    CEventLogger::LogError(
      0,
      String2,
      L"base\\diagnosis\\ra\\racommon\\src\\stringutils.cpp",
      0x2C8u,
      L"GetPropertyValueFromBlob",
      0x80004003);
  }
  return v6;
}

```

## disassembly

```asm
0x1400156c8  push    rbx
0x1400156ca  push    rbp
0x1400156cb  push    rsi
0x1400156cc  push    rdi
0x1400156cd  push    r12
0x1400156cf  push    r13
0x1400156d1  push    r14
0x1400156d3  push    r15
0x1400156d5  sub     rsp, 38h
0x1400156d9  xor     r14d, r14d
0x1400156dc  mov     r15, r8
0x1400156df  mov     rbp, rdx
0x1400156e2  mov     rbx, rcx
0x1400156e5  mov     r12d, r14d
0x1400156e8  test    rcx, rcx
0x1400156eb  jnz     short loc_140015700
0x1400156ed  mov     [rsp+78h+var_50], 80004003h
0x1400156f5  mov     r9d, 2C8h
0x1400156fb  jmp     loc_1400158AC
0x140015700  test    rbp, rbp
0x140015703  jnz     short loc_140015718
0x140015705  mov     [rsp+78h+var_50], 80004003h
0x14001570d  mov     r9d, 2C9h
0x140015713  jmp     loc_1400158AC
0x140015718  test    r15, r15
0x14001571b  jnz     short loc_140015730
0x14001571d  mov     [rsp+78h+var_50], 80004003h
0x140015725  mov     r9d, 2CAh
0x14001572b  jmp     loc_1400158AC
0x140015730  movzx   eax, word ptr [rcx]
0x140015733  test    ax, ax
0x140015736  jz      loc_14001589E
0x14001573c  cmp     [rdx], r14w
0x140015740  jz      loc_14001589E
0x140015746  or      rsi, 0FFFFFFFFFFFFFFFFh
0x14001574a  mov     rcx, rsi
0x14001574d  inc     rcx
0x140015750  cmp     [rbx+rcx*2], r14w
0x140015755  jnz     short loc_14001574D
0x140015757  lea     r13, [rbx+rcx*2]
0x14001575b  mov     rdi, rbx
0x14001575e  inc     rsi
0x140015761  cmp     [rdx+rsi*2], r14w
0x140015766  jnz     short loc_14001575E
0x140015768  mov     ecx, 3Bh ; ';'
0x14001576d  cmp     ax, cx
0x140015770  jz      short loc_14001579E
0x140015772  test    ax, ax
0x140015775  jz      short loc_140015795
0x140015777  movzx   ecx, ax; C
0x14001577a  call    cs:__imp_iswdigit
0x140015780  mov     ecx, 3Bh ; ';'
0x140015785  test    eax, eax
0x140015787  jz      short loc_140015795
0x140015789  add     rbx, 2
0x14001578d  movzx   eax, word ptr [rbx]
0x140015790  cmp     ax, cx
0x140015793  jnz     short loc_140015772
0x140015795  cmp     [rbx], cx
0x140015798  jnz     loc_1400158C4
0x14001579e  mov     rcx, rdi; String
0x1400157a1  mov     [rbx], r14w
0x1400157a5  call    cs:__imp__wtol
0x1400157ab  movsxd  rdi, eax
0x1400157ae  mov     word ptr [rbx], 3Bh ; ';'
0x1400157b3  cmp     rdi, rsi
0x1400157b6  jbe     loc_140015896
0x1400157bc  add     rbx, 2
0x1400157c0  mov     r14, rbx
0x1400157c3  movzx   eax, word ptr [rbx]
0x1400157c6  cmp     ax, 3Dh ; '='
0x1400157ca  jz      short loc_1400157F1
0x1400157cc  test    ax, ax
0x1400157cf  jz      short loc_1400157E7
0x1400157d1  lea     rax, [r14+rdi*2]
0x1400157d5  cmp     rbx, rax
0x1400157d8  jnb     short loc_1400157E7
0x1400157da  add     rbx, 2
0x1400157de  movzx   eax, word ptr [rbx]
0x1400157e1  cmp     ax, 3Dh ; '='
0x1400157e5  jnz     short loc_1400157CC
0x1400157e7  cmp     word ptr [rbx], 3Dh ; '='
0x1400157eb  jnz     loc_1400158C4
0x1400157f1  mov     r8d, esi; MaxCount
0x1400157f4  mov     rdx, rbp; String2
0x1400157f7  mov     rcx, r14; String1
0x1400157fa  call    wcsncmp_0
0x1400157ff  test    eax, eax
0x140015801  jz      short loc_14001581E
0x140015803  lea     rdi, [r14+rdi*2]
0x140015807  cmp     rdi, r13
0x14001580a  ja      loc_1400158C4
0x140015810  movzx   eax, word ptr [rdi]
0x140015813  mov     rbx, rdi
0x140015816  xor     r14d, r14d
0x140015819  jmp     loc_140015768
0x14001581e  lea     rax, [rsi+1]
0x140015822  cmp     rdi, rax
0x140015825  jz      loc_1400158C4
0x14001582b  sub     rdi, rsi
0x14001582e  lea     rsi, [rdi+rdi]
0x140015832  call    cs:__imp_GetProcessHeap
0x140015838  mov     r8, rsi; dwBytes
0x14001583b  mov     edx, 8; dwFlags
0x140015840  mov     rcx, rax; hHeap
0x140015843  call    cs:__imp_HeapAlloc
0x140015849  xor     ebp, ebp
0x14001584b  mov     [r15], rax
0x14001584e  test    rax, rax
0x140015851  jnz     short loc_140015863
0x140015853  mov     [rsp+78h+var_50], 8007000Eh
0x14001585b  mov     r9d, 30Ah
0x140015861  jmp     short loc_1400158AC
0x140015863  lea     r9, [rdi-1]; unsigned __int64
0x140015867  mov     rdx, rdi; unsigned __int64
0x14001586a  lea     r8, [rbx+2]; unsigned __int16 *
0x14001586e  mov     rcx, rax; unsigned __int16 *
0x140015871  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x140015876  test    eax, eax
0x140015878  jns     short loc_140015886
0x14001587a  mov     [rsp+78h+var_50], eax
0x14001587e  mov     r9d, 30Fh
0x140015884  jmp     short loc_1400158AC
0x140015886  mov     rcx, [r15]; this
0x140015889  mov     r12d, 1
0x14001588f  mov     [rsi+rcx-2], bp
0x140015894  jmp     short loc_1400158C4
0x140015896  mov     r9d, 2EFh
0x14001589c  jmp     short loc_1400158A4
0x14001589e  mov     r9d, 2CFh; unsigned int
0x1400158a4  mov     [rsp+78h+var_50], 80070057h; unsigned int
0x1400158ac  lea     rax, aGetpropertyval; "GetPropertyValueFromBlob"
0x1400158b3  lea     r8, aBaseDiagnosisR_7; "base\\diagnosis\\ra\\racommon\\src\\str"...
0x1400158ba  mov     [rsp+78h+var_58], rax; unsigned __int16 *
0x1400158bf  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x1400158c4  mov     eax, r12d
0x1400158c7  add     rsp, 38h
0x1400158cb  pop     r15
0x1400158cd  pop     r14
0x1400158cf  pop     r13
0x1400158d1  pop     r12
0x1400158d3  pop     rdi
0x1400158d4  pop     rsi
0x1400158d5  pop     rbp
0x1400158d6  pop     rbx
0x1400158d7  retn
```
