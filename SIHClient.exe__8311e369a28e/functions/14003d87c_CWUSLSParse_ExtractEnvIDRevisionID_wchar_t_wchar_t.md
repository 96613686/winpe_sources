# CWUSLSParse::ExtractEnvIDRevisionID(wchar_t * *,wchar_t * *)

- ea: `0x14003d87c`
- end: `0x14003dcf2`
- name: `?ExtractEnvIDRevisionID@CWUSLSParse@@QEAAJPEAPEA_W0@Z`
- size: `1142`
- prototype: `__int64 __fastcall(__int64 **this, wchar_t **, wchar_t **)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x1400338f4`

## callees

- `0x140008de4`
- `0x140010148`
- `0x14003d87c`
- `0x14004527c`
- `0x140045dc0`
- `0x14004cd00`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x14003d8f3`
- `OLEAUT32!__imp_SysAllocString` at `0x14003d9d5`
- `OLEAUT32!__imp_SysAllocString` at `0x14003db31`
- `OLEAUT32!__imp_SysAllocString` at `0x14003d8f3`
- `OLEAUT32!__imp_SysAllocString` at `0x14003d9d5`
- `OLEAUT32!__imp_SysAllocString` at `0x14003db31`
- `OLEAUT32!__imp_SysFreeString` at `0x14003db24`
- `OLEAUT32!__imp_SysFreeString` at `0x14003dc5f`
- `OLEAUT32!__imp_SysFreeString` at `0x14003dc8b`
- `OLEAUT32!__imp_SysFreeString` at `0x14003dcc7`
- `OLEAUT32!__imp_SysFreeString` at `0x14003db24`
- `OLEAUT32!__imp_SysFreeString` at `0x14003dc5f`
- `OLEAUT32!__imp_SysFreeString` at `0x14003dc8b`
- `OLEAUT32!__imp_SysFreeString` at `0x14003dcc7`
- `OLEAUT32!__imp_VariantInit` at `0x14003da87`
- `OLEAUT32!__imp_VariantInit` at `0x14003dbe3`
- `OLEAUT32!__imp_VariantInit` at `0x14003da87`
- `OLEAUT32!__imp_VariantInit` at `0x14003dbe3`
- `OLEAUT32!__imp_VariantClear` at `0x14003dade`
- `OLEAUT32!__imp_VariantClear` at `0x14003db04`
- `OLEAUT32!__imp_VariantClear` at `0x14003dc3a`
- `OLEAUT32!__imp_VariantClear` at `0x14003dc6b`
- `OLEAUT32!__imp_VariantClear` at `0x14003dade`
- `OLEAUT32!__imp_VariantClear` at `0x14003db04`
- `OLEAUT32!__imp_VariantClear` at `0x14003dc3a`
- `OLEAUT32!__imp_VariantClear` at `0x14003dc6b`

## string_xrefs

- `0x14003d8ec`: `/ServiceEnvironment`
- `0x14003da3b`: `Cannot find the ID tag within SLS response xml for environment.`
- `0x14003db97`: `Cannot find the revision tag within SLS response xml.`

## pseudocode

```c
__int64 __fastcall CWUSLSParse::ExtractEnvIDRevisionID(__int64 **this, wchar_t **a2, wchar_t **a3)
{
  __int64 v6; // rdx
  OLECHAR *v8; // rdi
  unsigned int v9; // esi
  __int64 *v10; // rcx
  __int64 v11; // rax
  int v12; // eax
  __int64 v13; // rdx
  __int64 v14; // rax
  int v15; // eax
  OLECHAR *v16; // rbx
  __int64 v17; // rax
  int v18; // eax
  int v19; // eax
  __int64 v20; // rdx
  __int64 v21; // rax
  int v22; // eax
  int v23; // eax
  __int64 v24; // rdx
  int v25; // [rsp+20h] [rbp-60h]
  const char *v26; // [rsp+28h] [rbp-58h]
  VARIANTARG pvarg; // [rsp+40h] [rbp-40h] BYREF
  __int64 v28; // [rsp+58h] [rbp-28h] BYREF
  __int64 *v29; // [rsp+60h] [rbp-20h] BYREF
  __int64 *v30; // [rsp+68h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]

  if ( !a2 )
  {
    v6 = 377;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\wusls.cpp",
      (const char *)0x80004003LL,
      v25);
    return 2147500035LL;
  }
  if ( !a3 )
  {
    v6 = 378;
    goto LABEL_3;
  }
  *a2 = 0;
  *a3 = 0;
  v8 = SysAllocString(L"/ServiceEnvironment");
  if ( v8 )
  {
    v30 = 0;
    v10 = *this;
    v11 = **this;
    v30 = 0;
    v12 = (*(__int64 (__fastcall **)(__int64 *, OLECHAR *, __int64 **))(v11 + 296))(v10, v8, &v30);
    v9 = v12;
    if ( v12 == 1 )
    {
      v9 = -2147023728;
      v13 = 391;
LABEL_12:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v13,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\wusls.cpp",
        (const char *)v9,
        v25);
LABEL_51:
      if ( v30 )
        (*(void (__fastcall **)(__int64 *))(*v30 + 16))(v30);
      goto LABEL_53;
    }
    if ( v12 < 0 )
    {
      v13 = 392;
      goto LABEL_12;
    }
    v29 = 0;
    v14 = *v30;
    v29 = 0;
    v15 = (*(__int64 (__fastcall **)(__int64 *, __int64 **))(v14 + 136))(v30, &v29);
    v9 = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x18B,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\wusls.cpp",
        (const char *)(unsigned int)v15,
        v25);
LABEL_49:
      if ( v29 )
        (*(void (__fastcall **)(__int64 *))(*v29 + 16))(v29);
      goto LABEL_51;
    }
    v16 = SysAllocString(L"ID");
    if ( v16 )
    {
      v28 = 0;
      v17 = *v29;
      v28 = 0;
      v18 = (*(__int64 (__fastcall **)(__int64 *, OLECHAR *, __int64 *))(v17 + 56))(v29, v16, &v28);
      v9 = v18;
      if ( v18 == 1 )
      {
        v9 = -2147023728;
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x196,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\wusls.cpp",
          (const char *)0x80070490LL,
          (int)"Cannot find the ID tag within SLS response xml for environment.",
          v26);
      }
      else if ( v18 >= 0 )
      {
        VariantInit(&pvarg);
        v19 = (*(__int64 (__fastcall **)(__int64, VARIANTARG *))(*(_QWORD *)v28 + 64LL))(v28, &pvarg);
        v9 = v19;
        if ( v19 >= 0 )
        {
          v19 = SusCopyBSTR(pvarg.bstrVal, a2);
          v9 = v19;
          if ( v19 >= 0 )
          {
            VariantClear(&pvarg);
            if ( v28 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
            SysFreeString(v16);
            v16 = SysAllocString(L"Revision");
            if ( v16 )
            {
              v28 = 0;
              v21 = *v29;
              v28 = 0;
              v22 = (*(__int64 (__fastcall **)(__int64 *, OLECHAR *, __int64 *))(v21 + 56))(v29, v16, &v28);
              v9 = v22;
              if ( v22 == 1 )
              {
                v9 = -2147023728;
                wil::details::in1diag3::Return_HrMsg(
                  retaddr,
                  (void *)0x1A7,
                  (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\wusls.cpp",
                  (const char *)0x80070490LL,
                  (int)"Cannot find the revision tag within SLS response xml.",
                  v26);
              }
              else if ( v22 >= 0 )
              {
                VariantInit(&pvarg);
                v23 = (*(__int64 (__fastcall **)(__int64, VARIANTARG *))(*(_QWORD *)v28 + 64LL))(v28, &pvarg);
                v9 = v23;
                if ( v23 >= 0 )
                {
                  v23 = SusCopyBSTR(pvarg.bstrVal, a3);
                  v9 = v23;
                  if ( v23 >= 0 )
                  {
                    VariantClear(&pvarg);
                    if ( v28 )
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
                    SysFreeString(v16);
                    v9 = 0;
                    goto LABEL_49;
                  }
                  v24 = 428;
                }
                else
                {
                  v24 = 427;
                }
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)v24,
                  (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\wusls.cpp",
                  (const char *)(unsigned int)v23,
                  v25);
                VariantClear(&pvarg);
              }
              else
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x1A8,
                  (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\wusls.cpp",
                  (const char *)(unsigned int)v22,
                  v25);
              }
              if ( v28 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
            }
            else
            {
              v9 = -2147024882;
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x1A1,
                (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\wusls.cpp",
                (const char *)0x8007000ELL,
                v25);
            }
            goto LABEL_44;
          }
          v20 = 411;
        }
        else
        {
          v20 = 410;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v20,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\wusls.cpp",
          (const char *)(unsigned int)v19,
          v25);
        VariantClear(&pvarg);
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x197,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\wusls.cpp",
          (const char *)(unsigned int)v18,
          v25);
      }
      if ( v28 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
    }
    else
    {
      v9 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x190,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\wusls.cpp",
        (const char *)0x8007000ELL,
        v25);
    }
LABEL_44:
    if ( v16 )
      SysFreeString(v16);
    goto LABEL_49;
  }
  v9 = -2147024882;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x180,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\wusls.cpp",
    (const char *)0x8007000ELL,
    v25);
LABEL_53:
  if ( v8 )
    SysFreeString(v8);
  return v9;
}

```

## disassembly

```asm
0x14003d87c  mov     [rsp-28h+arg_18], rbx
0x14003d881  push    rbp
0x14003d882  push    rsi
0x14003d883  push    rdi
0x14003d884  push    r14
0x14003d886  push    r15
0x14003d888  mov     rbp, rsp
0x14003d88b  sub     rsp, 80h
0x14003d892  mov     rax, cs:__security_cookie
0x14003d899  xor     rax, rsp
0x14003d89c  mov     [rbp+var_10], rax
0x14003d8a0  mov     r15, r8
0x14003d8a3  mov     r14, rdx
0x14003d8a6  mov     rbx, rcx
0x14003d8a9  test    rdx, rdx
0x14003d8ac  jnz     short loc_14003D8D2
0x14003d8ae  mov     edx, 179h; void *
0x14003d8b3  mov     ebx, 80004003h
0x14003d8b8  lea     r8, aCW1SSrcClientL_0; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x14003d8bf  mov     r9d, ebx; char *
0x14003d8c2  mov     rcx, [rbp+28h]; this
0x14003d8c6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003d8cb  mov     eax, ebx
0x14003d8cd  jmp     loc_14003DCCF
0x14003d8d2  test    r15, r15
0x14003d8d5  jnz     short loc_14003D8DE
0x14003d8d7  mov     edx, 17Ah
0x14003d8dc  jmp     short loc_14003D8B3
0x14003d8de  mov     qword ptr [rdx], 0
0x14003d8e5  mov     qword ptr [r8], 0
0x14003d8ec  lea     rcx, aServiceenviron; "/ServiceEnvironment"
0x14003d8f3  call    cs:__imp_SysAllocString
0x14003d8f9  mov     rdi, rax
0x14003d8fc  mov     [rbp+var_48], rax
0x14003d900  test    rax, rax
0x14003d903  jnz     short loc_14003D927
0x14003d905  mov     rcx, [rbp+28h]; this
0x14003d909  mov     esi, 8007000Eh
0x14003d90e  mov     r9d, esi; char *
0x14003d911  lea     r8, aCW1SSrcClientL_0; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x14003d918  mov     edx, 180h; void *
0x14003d91d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003d922  jmp     loc_14003DCBF
0x14003d927  mov     [rbp+var_18], 0
0x14003d92f  mov     rcx, [rbx]
0x14003d932  mov     rax, [rcx]
0x14003d935  mov     [rbp+var_18], 0
0x14003d93d  lea     r8, [rbp+var_18]
0x14003d941  mov     rdx, rdi
0x14003d944  mov     rax, [rax+128h]
0x14003d94b  call    _guard_dispatch_icall
0x14003d950  mov     esi, eax
0x14003d952  cmp     eax, 1
0x14003d955  jnz     short loc_14003D963
0x14003d957  mov     esi, 80070490h
0x14003d95c  mov     edx, 187h
0x14003d961  jmp     short loc_14003D96C
0x14003d963  test    eax, eax
0x14003d965  jns     short loc_14003D984
0x14003d967  mov     edx, 188h; void *
0x14003d96c  mov     rcx, [rbp+28h]; this
0x14003d970  mov     r9d, esi; char *
0x14003d973  lea     r8, aCW1SSrcClientL_0; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x14003d97a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003d97f  jmp     loc_14003DCA9
0x14003d984  mov     [rbp+var_20], 0
0x14003d98c  mov     rcx, [rbp+var_18]
0x14003d990  mov     rax, [rcx]
0x14003d993  mov     [rbp+var_20], 0
0x14003d99b  lea     rdx, [rbp+var_20]
0x14003d99f  mov     rax, [rax+88h]
0x14003d9a6  call    _guard_dispatch_icall
0x14003d9ab  mov     esi, eax
0x14003d9ad  test    eax, eax
0x14003d9af  jns     short loc_14003D9CE
0x14003d9b1  mov     rcx, [rbp+28h]; this
0x14003d9b5  mov     r9d, eax; char *
0x14003d9b8  lea     r8, aCW1SSrcClientL_0; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x14003d9bf  mov     edx, 18Bh; void *
0x14003d9c4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003d9c9  jmp     loc_14003DC93
0x14003d9ce  lea     rcx, aId_0; "ID"
0x14003d9d5  call    cs:__imp_SysAllocString
0x14003d9db  mov     rbx, rax
0x14003d9de  mov     [rbp+var_50], rax
0x14003d9e2  test    rax, rax
0x14003d9e5  jnz     short loc_14003DA09
0x14003d9e7  mov     rcx, [rbp+28h]; this
0x14003d9eb  mov     esi, 8007000Eh
0x14003d9f0  mov     r9d, esi; char *
0x14003d9f3  lea     r8, aCW1SSrcClientL_0; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x14003d9fa  mov     edx, 190h; void *
0x14003d9ff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003da04  jmp     loc_14003DAFB
0x14003da09  mov     [rbp+var_28], 0
0x14003da11  mov     rcx, [rbp+var_20]
0x14003da15  mov     rax, [rcx]
0x14003da18  mov     [rbp+var_28], 0
0x14003da20  lea     r8, [rbp+var_28]
0x14003da24  mov     rdx, rbx
0x14003da27  mov     rax, [rax+38h]
0x14003da2b  call    _guard_dispatch_icall
0x14003da30  mov     esi, eax
0x14003da32  cmp     eax, 1
0x14003da35  jnz     short loc_14003DA65
0x14003da37  mov     rcx, [rbp+28h]; this
0x14003da3b  lea     rax, aCannotFindTheI; "Cannot find the ID tag within SLS respo"...
0x14003da42  mov     qword ptr [rsp+80h+var_60], rax; int
0x14003da47  mov     esi, 80070490h
0x14003da4c  mov     r9d, esi; char *
0x14003da4f  lea     r8, aCW1SSrcClientL_0; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x14003da56  mov     edx, 196h; void *
0x14003da5b  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x14003da60  jmp     loc_14003DAE5
0x14003da65  test    eax, eax
0x14003da67  jns     short loc_14003DA83
0x14003da69  mov     rcx, [rbp+28h]; this
0x14003da6d  mov     r9d, eax; char *
0x14003da70  lea     r8, aCW1SSrcClientL_0; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x14003da77  mov     edx, 197h; void *
0x14003da7c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003da81  jmp     short loc_14003DAE5
0x14003da83  lea     rcx, [rbp+pvarg]; pvarg
0x14003da87  call    cs:__imp_VariantInit
0x14003da8d  nop
0x14003da8e  mov     rcx, [rbp+var_28]
0x14003da92  mov     rax, [rcx]
0x14003da95  lea     rdx, [rbp+pvarg]
0x14003da99  mov     rax, [rax+40h]
0x14003da9d  call    _guard_dispatch_icall
0x14003daa2  mov     esi, eax
0x14003daa4  test    eax, eax
0x14003daa6  jns     short loc_14003DAAF
0x14003daa8  mov     edx, 19Ah
0x14003daad  jmp     short loc_14003DAC6
0x14003daaf  mov     rdx, r14; wchar_t **
0x14003dab2  mov     rcx, qword ptr [rbp+pvarg+8]; strIn
0x14003dab6  call    ?SusCopyBSTR@@YAJPEA_WPEAPEA_W@Z; SusCopyBSTR(wchar_t *,wchar_t * *)
0x14003dabb  mov     esi, eax
0x14003dabd  test    eax, eax
0x14003dabf  jns     short loc_14003DB00
0x14003dac1  mov     edx, 19Bh; void *
0x14003dac6  mov     r9d, eax; char *
0x14003dac9  lea     r8, aCW1SSrcClientL_0; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x14003dad0  mov     rcx, [rbp+28h]; this
0x14003dad4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003dad9  nop
0x14003dada  lea     rcx, [rbp+pvarg]; pvarg
0x14003dade  call    cs:__imp_VariantClear
0x14003dae4  nop
0x14003dae5  mov     rcx, [rbp+var_28]
0x14003dae9  test    rcx, rcx
0x14003daec  jz      short loc_14003DAFB
0x14003daee  mov     rax, [rcx]
0x14003daf1  mov     rax, [rax+10h]
0x14003daf5  call    _guard_dispatch_icall
0x14003dafa  nop
0x14003dafb  jmp     loc_14003DC57
0x14003db00  lea     rcx, [rbp+pvarg]; pvarg
0x14003db04  call    cs:__imp_VariantClear
0x14003db0a  nop
0x14003db0b  mov     rcx, [rbp+var_28]
0x14003db0f  test    rcx, rcx
0x14003db12  jz      short loc_14003DB21
0x14003db14  mov     rax, [rcx]
0x14003db17  mov     rax, [rax+10h]
0x14003db1b  call    _guard_dispatch_icall
0x14003db20  nop
0x14003db21  mov     rcx, rbx; bstrString
0x14003db24  call    cs:__imp_SysFreeString
0x14003db2a  lea     rcx, aRevision; "Revision"
0x14003db31  call    cs:__imp_SysAllocString
0x14003db37  mov     rbx, rax
0x14003db3a  mov     [rbp+var_50], rax
0x14003db3e  test    rax, rax
0x14003db41  jnz     short loc_14003DB65
0x14003db43  mov     rcx, [rbp+28h]; this
0x14003db47  mov     esi, 8007000Eh
0x14003db4c  mov     r9d, esi; char *
0x14003db4f  lea     r8, aCW1SSrcClientL_0; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x14003db56  mov     edx, 1A1h; void *
0x14003db5b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003db60  jmp     loc_14003DC57
0x14003db65  mov     [rbp+var_28], 0
0x14003db6d  mov     rcx, [rbp+var_20]
0x14003db71  mov     rax, [rcx]
0x14003db74  mov     [rbp+var_28], 0
0x14003db7c  lea     r8, [rbp+var_28]
0x14003db80  mov     rdx, rbx
0x14003db83  mov     rax, [rax+38h]
0x14003db87  call    _guard_dispatch_icall
0x14003db8c  mov     esi, eax
0x14003db8e  cmp     eax, 1
0x14003db91  jnz     short loc_14003DBC1
0x14003db93  mov     rcx, [rbp+28h]; this
0x14003db97  lea     rax, aCannotFindTheR; "Cannot find the revision tag within SLS"...
0x14003db9e  mov     qword ptr [rsp+80h+var_60], rax; int
0x14003dba3  mov     esi, 80070490h
0x14003dba8  mov     r9d, esi; char *
0x14003dbab  lea     r8, aCW1SSrcClientL_0; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x14003dbb2  mov     edx, 1A7h; void *
0x14003dbb7  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x14003dbbc  jmp     loc_14003DC41
0x14003dbc1  test    eax, eax
0x14003dbc3  jns     short loc_14003DBDF
0x14003dbc5  mov     rcx, [rbp+28h]; this
0x14003dbc9  mov     r9d, eax; char *
0x14003dbcc  lea     r8, aCW1SSrcClientL_0; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x14003dbd3  mov     edx, 1A8h; void *
0x14003dbd8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003dbdd  jmp     short loc_14003DC41
0x14003dbdf  lea     rcx, [rbp+pvarg]; pvarg
0x14003dbe3  call    cs:__imp_VariantInit
0x14003dbe9  nop
0x14003dbea  mov     rcx, [rbp+var_28]
0x14003dbee  mov     rax, [rcx]
0x14003dbf1  lea     rdx, [rbp+pvarg]
0x14003dbf5  mov     rax, [rax+40h]
0x14003dbf9  call    _guard_dispatch_icall
0x14003dbfe  mov     esi, eax
0x14003dc00  test    eax, eax
0x14003dc02  jns     short loc_14003DC0B
0x14003dc04  mov     edx, 1ABh
0x14003dc09  jmp     short loc_14003DC22
0x14003dc0b  mov     rdx, r15; wchar_t **
0x14003dc0e  mov     rcx, qword ptr [rbp+pvarg+8]; strIn
0x14003dc12  call    ?SusCopyBSTR@@YAJPEA_WPEAPEA_W@Z; SusCopyBSTR(wchar_t *,wchar_t * *)
0x14003dc17  mov     esi, eax
0x14003dc19  test    eax, eax
0x14003dc1b  jns     short loc_14003DC67
0x14003dc1d  mov     edx, 1ACh; void *
0x14003dc22  mov     r9d, eax; char *
0x14003dc25  lea     r8, aCW1SSrcClientL_0; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x14003dc2c  mov     rcx, [rbp+28h]; this
0x14003dc30  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003dc35  nop
0x14003dc36  lea     rcx, [rbp+pvarg]; pvarg
0x14003dc3a  call    cs:__imp_VariantClear
0x14003dc40  nop
0x14003dc41  mov     rcx, [rbp+var_28]
0x14003dc45  test    rcx, rcx
0x14003dc48  jz      short loc_14003DC57
0x14003dc4a  mov     rax, [rcx]
0x14003dc4d  mov     rax, [rax+10h]
0x14003dc51  call    _guard_dispatch_icall
0x14003dc56  nop
0x14003dc57  test    rbx, rbx
0x14003dc5a  jz      short loc_14003DC93
0x14003dc5c  mov     rcx, rbx; bstrString
0x14003dc5f  call    cs:__imp_SysFreeString
0x14003dc65  jmp     short loc_14003DC93
0x14003dc67  lea     rcx, [rbp+pvarg]; pvarg
0x14003dc6b  call    cs:__imp_VariantClear
0x14003dc71  nop
0x14003dc72  mov     rcx, [rbp+var_28]
0x14003dc76  test    rcx, rcx
0x14003dc79  jz      short loc_14003DC88
0x14003dc7b  mov     rax, [rcx]
0x14003dc7e  mov     rax, [rax+10h]
0x14003dc82  call    _guard_dispatch_icall
0x14003dc87  nop
0x14003dc88  mov     rcx, rbx; bstrString
0x14003dc8b  call    cs:__imp_SysFreeString
0x14003dc91  xor     esi, esi
0x14003dc93  mov     rcx, [rbp+var_20]
0x14003dc97  test    rcx, rcx
0x14003dc9a  jz      short loc_14003DCA9
0x14003dc9c  mov     rax, [rcx]
0x14003dc9f  mov     rax, [rax+10h]
0x14003dca3  call    _guard_dispatch_icall
0x14003dca8  nop
0x14003dca9  mov     rcx, [rbp+var_18]
0x14003dcad  test    rcx, rcx
0x14003dcb0  jz      short loc_14003DCBF
0x14003dcb2  mov     rax, [rcx]
0x14003dcb5  mov     rax, [rax+10h]
0x14003dcb9  call    _guard_dispatch_icall
0x14003dcbe  nop
0x14003dcbf  test    rdi, rdi
0x14003dcc2  jz      short loc_14003DCCD
0x14003dcc4  mov     rcx, rdi; bstrString
0x14003dcc7  call    cs:__imp_SysFreeString
0x14003dccd  mov     eax, esi
0x14003dccf  mov     rcx, [rbp+var_10]
0x14003dcd3  xor     rcx, rsp; StackCookie
0x14003dcd6  call    __security_check_cookie
0x14003dcdb  mov     rbx, [rsp+80h+arg_18]
0x14003dce3  add     rsp, 80h
0x14003dcea  pop     r15
0x14003dcec  pop     r14
0x14003dcee  pop     rdi
0x14003dcef  pop     rsi
0x14003dcf0  pop     rbp
0x14003dcf1  retn
```
