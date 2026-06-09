# CSearchQueryHelper::_InitializeDefaultStringProperty(IQueryParser2 *,wchar_t const *)

- ea: `0x18003ba88`
- end: `0x18003bc1f`
- name: `?_InitializeDefaultStringProperty@CSearchQueryHelper@@AEAAJPEAUIQueryParser2@@PEB_W@Z`
- size: `407`
- prototype: `__int64 __fastcall(CSearchQueryHelper *this, struct IQueryParser2 *, const wchar_t *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18003b8f4`
- `0x180073970`

## callees

- `0x180020250`
- `0x18003ba88`
- `0x18003bc28`
- `0x18003bed0`
- `0x18008b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003bbf5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003bc03`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003bbf5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003bc03`

## pseudocode

```c
__int64 __fastcall CSearchQueryHelper::_InitializeDefaultStringProperty(
        CSearchQueryHelper *this,
        struct IQueryParser2 *a2,
        const wchar_t *a3)
{
  int v5; // ebx
  unsigned __int64 v6; // rdi
  void *v7; // rcx
  CSearchQueryHelper *v8; // rcx
  const wchar_t **v9; // rsi
  const wchar_t *v10; // r14
  __int64 v11; // rax
  __int64 v12; // rax
  unsigned __int64 i; // rdi
  LPVOID pv; // [rsp+30h] [rbp-20h] BYREF
  __int16 v16; // [rsp+38h] [rbp-18h] BYREF
  _BYTE v17[22]; // [rsp+3Ah] [rbp-16h]
  unsigned __int64 v18; // [rsp+80h] [rbp+30h] BYREF
  unsigned __int64 v19; // [rsp+98h] [rbp+48h] BYREF

  v18 = 0;
  v5 = CSearchQueryHelper::_ParseStringList(this, a3, 0, 0, 0, &v18);
  if ( v5 >= 0 )
  {
    v6 = v18;
    pv = 0;
    v19 = 0;
    v5 = ULongLongMult(v18, 8u, &v19);
    if ( v5 >= 0 )
    {
      v5 = CTCoAllocPolicy::Alloc(v7, 1u, v19, &pv);
      if ( v5 >= 0 )
      {
        v9 = (const wchar_t **)pv;
        v18 = 0;
        v5 = CSearchQueryHelper::_ParseStringList(v8, a3, 0, (wchar_t **)pv, v6, &v18);
        if ( v5 >= 0 )
        {
          if ( v6 )
          {
            if ( v6 == 1 )
            {
              v10 = *v9;
            }
            else
            {
              v10 = L"System.Generic.String";
              v16 = 4127;
              v11 = *(_QWORD *)a2;
              *(_OWORD *)v17 = 0;
              *(_DWORD *)&v17[6] = v6;
              *(_QWORD *)&v17[14] = v9;
              v5 = (*(__int64 (__fastcall **)(struct IQueryParser2 *, __int64, const wchar_t *, __int16 *))(v11 + 48))(
                     a2,
                     3,
                     L"System.Generic.String",
                     &v16);
            }
            if ( v5 >= 0 )
            {
              v16 = 31;
              *(_OWORD *)v17 = 0;
              v12 = *(_QWORD *)a2;
              *(_OWORD *)&v17[6] = (unsigned __int64)v10;
              v5 = (*(__int64 (__fastcall **)(struct IQueryParser2 *, __int64, const WCHAR *, __int16 *))(v12 + 48))(
                     a2,
                     1,
                     L"System.StructuredQueryType.String",
                     &v16);
            }
          }
          else
          {
            v5 = -2147024809;
          }
          for ( i = v18; i; CoTaskMemFree((LPVOID)v9[i]) )
            --i;
        }
        CoTaskMemFree(v9);
      }
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18003ba88  mov     r11, rsp
0x18003ba8b  mov     [r11+10h], rbx
0x18003ba8f  mov     [r11+8], rcx
0x18003ba93  push    rbp
0x18003ba94  push    rsi
0x18003ba95  push    rdi
0x18003ba96  push    r14
0x18003ba98  push    r15
0x18003ba9a  mov     rbp, rsp
0x18003ba9d  sub     rsp, 50h
0x18003baa1  mov     r14, r8
0x18003baa4  mov     [rbp+arg_0], 0
0x18003baac  lea     rax, [rbp+arg_0]
0x18003bab0  mov     r15, rdx
0x18003bab3  mov     [r11-50h], rax
0x18003bab7  mov     rdx, r14; wchar_t *
0x18003baba  xor     r9d, r9d; wchar_t **
0x18003babd  mov     qword ptr [r11-58h], 0
0x18003bac5  xor     r8d, r8d; unsigned __int64
0x18003bac8  call    ?_ParseStringList@CSearchQueryHelper@@AEAAJPEB_W_KPEAPEA_W1PEA_K@Z; CSearchQueryHelper::_ParseStringList(wchar_t const *,unsigned __int64,wchar_t * *,unsigned __int64,unsigned __int64 *)
0x18003bacd  mov     ebx, eax
0x18003bacf  test    eax, eax
0x18003bad1  js      loc_18003BC09
0x18003bad7  mov     rdi, [rbp+arg_0]
0x18003badb  lea     r8, [rbp+arg_18]; unsigned __int64 *
0x18003badf  mov     rcx, rdi; unsigned __int64
0x18003bae2  mov     [rbp+pv], 0
0x18003baea  mov     edx, 8; unsigned __int64
0x18003baef  mov     [rbp+arg_18], 0
0x18003baf7  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18003bafc  mov     ebx, eax
0x18003bafe  test    eax, eax
0x18003bb00  js      loc_18003BC09
0x18003bb06  mov     r8, [rbp+arg_18]; unsigned __int64
0x18003bb0a  lea     r9, [rbp+pv]; void **
0x18003bb0e  mov     edx, 1; unsigned int
0x18003bb13  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x18003bb18  mov     ebx, eax
0x18003bb1a  test    eax, eax
0x18003bb1c  js      loc_18003BC09
0x18003bb22  mov     rsi, [rbp+pv]
0x18003bb26  lea     rax, [rbp+arg_0]
0x18003bb2a  mov     [rsp+50h+var_28], rax; unsigned __int64 *
0x18003bb2f  mov     r9, rsi; wchar_t **
0x18003bb32  xor     r8d, r8d; unsigned __int64
0x18003bb35  mov     [rsp+50h+var_30], rdi; unsigned __int64
0x18003bb3a  mov     rdx, r14; wchar_t *
0x18003bb3d  mov     [rbp+arg_0], 0
0x18003bb45  call    ?_ParseStringList@CSearchQueryHelper@@AEAAJPEB_W_KPEAPEA_W1PEA_K@Z; CSearchQueryHelper::_ParseStringList(wchar_t const *,unsigned __int64,wchar_t * *,unsigned __int64,unsigned __int64 *)
0x18003bb4a  mov     ebx, eax
0x18003bb4c  test    eax, eax
0x18003bb4e  js      loc_18003BC00
0x18003bb54  test    rdi, rdi
0x18003bb57  jnz     short loc_18003BB63
0x18003bb59  mov     ebx, 80070057h
0x18003bb5e  jmp     loc_18003BBE8
0x18003bb63  cmp     rdi, 1
0x18003bb67  jnz     short loc_18003BB6E
0x18003bb69  mov     r14, [rsi]
0x18003bb6c  jmp     short loc_18003BBA9
0x18003bb6e  mov     eax, 101Fh
0x18003bb73  lea     r14, aSystemGenericS; "System.Generic.String"
0x18003bb7a  mov     [rbp+var_18], ax
0x18003bb7e  lea     r9, [rbp+var_18]
0x18003bb82  mov     rax, [r15]
0x18003bb85  xorps   xmm0, xmm0
0x18003bb88  movups  xmmword ptr [rbp+var_16], xmm0
0x18003bb8c  mov     r8, r14
0x18003bb8f  mov     dword ptr [rbp+var_16+6], edi
0x18003bb92  mov     edx, 3
0x18003bb97  mov     qword ptr [rbp+var_16+0Eh], rsi
0x18003bb9b  mov     rax, [rax+30h]
0x18003bb9f  mov     rcx, r15
0x18003bba2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bba7  mov     ebx, eax
0x18003bba9  test    ebx, ebx
0x18003bbab  js      short loc_18003BBE8
0x18003bbad  mov     eax, 1Fh
0x18003bbb2  lea     r9, [rbp+var_18]
0x18003bbb6  mov     [rbp+var_18], ax
0x18003bbba  lea     r8, aSystemStructur_24; "System.StructuredQueryType.String"
0x18003bbc1  xor     eax, eax
0x18003bbc3  xorps   xmm0, xmm0
0x18003bbc6  movups  xmmword ptr [rbp+var_16], xmm0
0x18003bbca  mov     qword ptr [rbp+var_16+0Eh], rax
0x18003bbce  mov     edx, 1
0x18003bbd3  mov     rax, [r15]
0x18003bbd6  mov     rcx, r15
0x18003bbd9  mov     qword ptr [rbp+var_16+6], r14
0x18003bbdd  mov     rax, [rax+30h]
0x18003bbe1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bbe6  mov     ebx, eax
0x18003bbe8  mov     rdi, [rbp+arg_0]
0x18003bbec  jmp     short loc_18003BBFB
0x18003bbee  dec     rdi
0x18003bbf1  mov     rcx, [rsi+rdi*8]; pv
0x18003bbf5  call    cs:__imp_CoTaskMemFree
0x18003bbfb  test    rdi, rdi
0x18003bbfe  jnz     short loc_18003BBEE
0x18003bc00  mov     rcx, rsi; pv
0x18003bc03  call    cs:__imp_CoTaskMemFree
0x18003bc09  mov     eax, ebx
0x18003bc0b  mov     rbx, [rsp+50h+arg_8]
0x18003bc13  add     rsp, 50h
0x18003bc17  pop     r15
0x18003bc19  pop     r14
0x18003bc1b  pop     rdi
0x18003bc1c  pop     rsi
0x18003bc1d  pop     rbp
0x18003bc1e  retn
```
