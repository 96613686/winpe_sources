# PropvarCvt::PropVariantConvertStrToWStr(tagPROPVARIANT *,uint)

- ea: `0x18002b428`
- end: `0x18002b6ed`
- name: `?PropVariantConvertStrToWStr@PropvarCvt@@YAJPEAUtagPROPVARIANT@@I@Z`
- size: `709`
- prototype: `__int64 __fastcall(PropvarCvt *this, struct tagPROPVARIANT *)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002636c`
- `0x18002b428`

## callees

- `0x180017870`
- `0x18001870c`
- `0x18002b20c`
- `0x18002b3a4`
- `0x18002b428`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002b4fc`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002b521`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002b55b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002b697`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002b4fc`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002b521`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002b55b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002b697`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002b4d2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002b4d2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b5cc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b5ef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b6c5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b5cc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b5ef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b6c5`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18002b4ab`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18002b4ab`

## pseudocode

```c
__int64 __fastcall PropvarCvt::PropVariantConvertStrToWStr(PropvarCvt *this, struct tagPROPVARIANT *a2)
{
  UINT v2; // r15d
  HRESULT TaskMemWStrFromStr; // ebx
  unsigned int v6; // r8d
  unsigned int v7; // r8d
  LPVOID v8; // rax
  PROPVARIANT *v9; // rsi
  unsigned int v10; // esi
  const CHAR *v11; // rdx
  PROPVARIANT *v12; // rcx
  PROPVARIANT *v13; // rcx
  unsigned int i; // esi
  const CHAR *v15; // rdx
  PROPVARIANT *v16; // rcx
  PROPVARIANT pvarDest[2]; // [rsp+20h] [rbp-20h] BYREF
  void *v18; // [rsp+30h] [rbp-10h]
  PROPVARIANT *pvar; // [rsp+70h] [rbp+30h] BYREF

  v2 = (unsigned int)a2;
  if ( !this )
    return 2147500035LL;
  TaskMemWStrFromStr = 0;
  if ( (unsigned int)PropVariantContainsStr() )
  {
    if ( *(_WORD *)this == 30 )
    {
      v15 = (const CHAR *)*((_QWORD *)this + 1);
      if ( v15 )
      {
        pvar = 0;
        pvarDest[0] = &pvar;
        pvarDest[1] = 0;
        LOBYTE(v18) = 1;
        TaskMemWStrFromStr = CreateTaskMemWStrFromStr(v2, v15);
        wil::details::out_param_t<wistd::unique_ptr<wchar_t,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<wchar_t,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(pvarDest);
        if ( TaskMemWStrFromStr < 0
          || (TaskMemWStrFromStr = PropVariantClear((PROPVARIANT *)this), TaskMemWStrFromStr < 0) )
        {
          v16 = pvar;
        }
        else
        {
          *(_WORD *)this = 31;
          v16 = 0;
          *((_QWORD *)this + 1) = pvar;
          TaskMemWStrFromStr = 0;
        }
        pvar = 0;
        if ( v16 )
          CoTaskMemFree(v16);
        return (unsigned int)TaskMemWStrFromStr;
      }
    }
    else if ( *(_WORD *)this == 4108 )
    {
      if ( *((_QWORD *)this + 2) )
      {
        for ( i = 0;
              i < *((_DWORD *)this + 2);
              TaskMemWStrFromStr = PropvarCvt::PropVariantConvertStrToWStr(
                                     (PropvarCvt *)(*((_QWORD *)this + 2) + 24LL * i++),
                                     (struct tagPROPVARIANT *)v2,
                                     v6) )
        {
          if ( TaskMemWStrFromStr < 0 )
            break;
        }
        return (unsigned int)TaskMemWStrFromStr;
      }
    }
    else
    {
      if ( *(_WORD *)this != 4126 )
      {
        if ( *(_WORD *)this == 16396 )
        {
          *(_OWORD *)pvarDest = 0;
          v18 = 0;
          TaskMemWStrFromStr = PropVariantCopy(pvarDest, *((const PROPVARIANT **)this + 1));
          if ( TaskMemWStrFromStr >= 0 )
            TaskMemWStrFromStr = PropvarCvt::PropVariantConvertStrToWStr(
                                   (PropvarCvt *)pvarDest,
                                   (struct tagPROPVARIANT *)v2,
                                   v7);
          pvar = 0;
          if ( TaskMemWStrFromStr >= 0 )
          {
            v8 = CoTaskMemAlloc(0x18u);
            wistd::unique_ptr<tagPROPVARIANT,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
              &pvar,
              v8);
            v9 = pvar;
            if ( pvar )
            {
              *(_OWORD *)pvar = 0;
              v9[2] = 0;
              TaskMemWStrFromStr = PropVariantClear(v9);
              if ( TaskMemWStrFromStr >= 0 )
              {
                *(_OWORD *)v9 = *(_OWORD *)pvarDest;
                v9[2] = v18;
                LOWORD(pvarDest[0]) = 0;
                TaskMemWStrFromStr = PropVariantClear((PROPVARIANT *)this);
                if ( TaskMemWStrFromStr >= 0 )
                {
                  *(_WORD *)this = 4108;
                  *((_DWORD *)this + 2) = 1;
                  pvar = 0;
                  *((_QWORD *)this + 2) = v9;
                  TaskMemWStrFromStr = 0;
                }
              }
            }
            else
            {
              TaskMemWStrFromStr = -2147024882;
            }
          }
          wistd::unique_ptr<tagPROPVARIANT,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
            &pvar,
            0);
          PropVariantClear(pvarDest);
        }
        return (unsigned int)TaskMemWStrFromStr;
      }
      if ( *((_QWORD *)this + 2) )
      {
        v10 = 0;
        if ( *((_DWORD *)this + 2) )
        {
          while ( TaskMemWStrFromStr >= 0 )
          {
            v11 = *(const CHAR **)(*((_QWORD *)this + 2) + 8LL * v10);
            if ( v11 )
            {
              pvar = 0;
              pvarDest[0] = &pvar;
              pvarDest[1] = 0;
              LOBYTE(v18) = 1;
              TaskMemWStrFromStr = CreateTaskMemWStrFromStr(v2, v11);
              wil::details::out_param_t<wistd::unique_ptr<wchar_t,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<wchar_t,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(pvarDest);
              if ( TaskMemWStrFromStr >= 0 )
              {
                CoTaskMemFree(*(LPVOID *)(*((_QWORD *)this + 2) + 8LL * v10));
                v12 = pvar;
                pvar = 0;
                *(_QWORD *)(*((_QWORD *)this + 2) + 8LL * v10) = v12;
              }
              v13 = pvar;
              pvar = 0;
              if ( v13 )
                CoTaskMemFree(v13);
            }
            else
            {
              TaskMemWStrFromStr = -2147467261;
            }
            if ( ++v10 >= *((_DWORD *)this + 2) )
            {
              if ( TaskMemWStrFromStr < 0 )
                return (unsigned int)TaskMemWStrFromStr;
              goto LABEL_28;
            }
          }
        }
        else
        {
LABEL_28:
          *(_WORD *)this = 4127;
          return 0;
        }
        return (unsigned int)TaskMemWStrFromStr;
      }
    }
    return (unsigned int)-2147467261;
  }
  return (unsigned int)TaskMemWStrFromStr;
}

```

## disassembly

```asm
0x18002b428  mov     [rsp-28h+arg_8], rbx
0x18002b42d  mov     [rsp-28h+arg_10], rsi
0x18002b432  push    rbp
0x18002b433  push    rdi
0x18002b434  push    r12
0x18002b436  push    r14
0x18002b438  push    r15
0x18002b43a  mov     rbp, rsp
0x18002b43d  sub     rsp, 40h
0x18002b441  mov     r15d, edx
0x18002b444  mov     rdi, rcx
0x18002b447  xor     r12d, r12d
0x18002b44a  test    rcx, rcx
0x18002b44d  jnz     short loc_18002B459
0x18002b44f  mov     eax, 80004003h
0x18002b454  jmp     loc_18002B6D4
0x18002b459  mov     ebx, r12d
0x18002b45c  call    PropVariantContainsStr
0x18002b461  test    eax, eax
0x18002b463  jz      loc_18002B6D2
0x18002b469  movzx   ecx, word ptr [rdi]
0x18002b46c  sub     ecx, 1Eh
0x18002b46f  jz      loc_18002B65C
0x18002b475  sub     ecx, 0FEEh
0x18002b47b  jz      loc_18002B61C
0x18002b481  sub     ecx, 12h
0x18002b484  jz      loc_18002B566
0x18002b48a  cmp     ecx, 2FEEh
0x18002b490  jnz     loc_18002B6D2
0x18002b496  xorps   xmm0, xmm0
0x18002b499  xor     eax, eax
0x18002b49b  movups  xmmword ptr [rbp+pvarDest], xmm0
0x18002b49f  mov     [rbp+var_10], rax
0x18002b4a3  mov     rdx, [rdi+8]; pvarSrc
0x18002b4a7  lea     rcx, [rbp+pvarDest]; pvarDest
0x18002b4ab  call    cs:__imp_PropVariantCopy
0x18002b4b1  mov     ebx, eax
0x18002b4b3  test    eax, eax
0x18002b4b5  js      short loc_18002B4C5
0x18002b4b7  mov     edx, r15d; struct tagPROPVARIANT *
0x18002b4ba  lea     rcx, [rbp+pvarDest]; this
0x18002b4be  call    ?PropVariantConvertStrToWStr@PropvarCvt@@YAJPEAUtagPROPVARIANT@@I@Z; PropvarCvt::PropVariantConvertStrToWStr(tagPROPVARIANT *,uint)
0x18002b4c3  mov     ebx, eax
0x18002b4c5  mov     [rbp+pvar], r12
0x18002b4c9  test    ebx, ebx
0x18002b4cb  js      short loc_18002B54B
0x18002b4cd  mov     ecx, 18h; cb
0x18002b4d2  call    cs:__imp_CoTaskMemAlloc
0x18002b4d8  mov     rdx, rax
0x18002b4db  lea     rcx, [rbp+pvar]
0x18002b4df  call    ?reset@?$unique_ptr@UtagPROPVARIANT@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAXPEAUtagPROPVARIANT@@@Z; wistd::unique_ptr<tagPROPVARIANT,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::reset(tagPROPVARIANT *)
0x18002b4e4  mov     rsi, [rbp+pvar]
0x18002b4e8  test    rsi, rsi
0x18002b4eb  jz      short loc_18002B546
0x18002b4ed  xorps   xmm0, xmm0
0x18002b4f0  xor     eax, eax
0x18002b4f2  movups  xmmword ptr [rsi], xmm0
0x18002b4f5  mov     [rsi+10h], rax
0x18002b4f9  mov     rcx, rsi; pvar
0x18002b4fc  call    cs:__imp_PropVariantClear
0x18002b502  mov     ebx, eax
0x18002b504  test    eax, eax
0x18002b506  js      short loc_18002B54B
0x18002b508  movups  xmm0, xmmword ptr [rbp+pvarDest]
0x18002b50c  movups  xmmword ptr [rsi], xmm0
0x18002b50f  movsd   xmm1, [rbp+var_10]
0x18002b514  movsd   qword ptr [rsi+10h], xmm1
0x18002b519  mov     word ptr [rbp+pvarDest], r12w
0x18002b51e  mov     rcx, rdi; pvar
0x18002b521  call    cs:__imp_PropVariantClear
0x18002b527  mov     ebx, eax
0x18002b529  test    eax, eax
0x18002b52b  js      short loc_18002B54B
0x18002b52d  mov     word ptr [rdi], 100Ch
0x18002b532  mov     dword ptr [rdi+8], 1
0x18002b539  mov     [rbp+pvar], r12
0x18002b53d  mov     [rdi+10h], rsi
0x18002b541  mov     ebx, r12d
0x18002b544  jmp     short loc_18002B54B
0x18002b546  mov     ebx, 8007000Eh
0x18002b54b  xor     edx, edx
0x18002b54d  lea     rcx, [rbp+pvar]
0x18002b551  call    ?reset@?$unique_ptr@UtagPROPVARIANT@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAXPEAUtagPROPVARIANT@@@Z; wistd::unique_ptr<tagPROPVARIANT,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::reset(tagPROPVARIANT *)
0x18002b556  nop
0x18002b557  lea     rcx, [rbp+pvarDest]; pvar
0x18002b55b  call    cs:__imp_PropVariantClear
0x18002b561  jmp     loc_18002B6D2
0x18002b566  cmp     [rdi+10h], r12
0x18002b56a  jz      loc_18002B6CD
0x18002b570  mov     esi, r12d
0x18002b573  cmp     [rdi+8], r12d
0x18002b577  jbe     loc_18002B60F
0x18002b57d  test    ebx, ebx
0x18002b57f  js      loc_18002B6D2
0x18002b585  mov     r14d, esi
0x18002b588  mov     rax, [rdi+10h]
0x18002b58c  mov     rdx, [rax+r14*8]; lpMultiByteStr
0x18002b590  test    rdx, rdx
0x18002b593  jz      short loc_18002B5F7
0x18002b595  mov     [rbp+pvar], r12
0x18002b599  lea     rax, [rbp+pvar]
0x18002b59d  mov     [rbp+pvarDest], rax
0x18002b5a1  mov     [rbp+pvarDest+8], r12
0x18002b5a5  mov     byte ptr [rbp+var_10], 1
0x18002b5a9  lea     r8, [rbp+pvarDest+8]
0x18002b5ad  mov     ecx, r15d; CodePage
0x18002b5b0  call    CreateTaskMemWStrFromStr
0x18002b5b5  mov     ebx, eax
0x18002b5b7  lea     rcx, [rbp+pvarDest]
0x18002b5bb  call    ??1?$out_param_t@V?$unique_ptr@_WU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<wchar_t,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<wchar_t,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x18002b5c0  test    ebx, ebx
0x18002b5c2  js      short loc_18002B5E2
0x18002b5c4  mov     rcx, [rdi+10h]
0x18002b5c8  mov     rcx, [rcx+r14*8]; pv
0x18002b5cc  call    cs:__imp_CoTaskMemFree
0x18002b5d2  mov     rcx, [rbp+pvar]
0x18002b5d6  mov     [rbp+pvar], r12
0x18002b5da  mov     rax, [rdi+10h]
0x18002b5de  mov     [rax+r14*8], rcx
0x18002b5e2  mov     rcx, [rbp+pvar]; pv
0x18002b5e6  mov     [rbp+pvar], r12
0x18002b5ea  test    rcx, rcx
0x18002b5ed  jz      short loc_18002B5FC
0x18002b5ef  call    cs:__imp_CoTaskMemFree
0x18002b5f5  jmp     short loc_18002B5FC
0x18002b5f7  mov     ebx, 80004003h
0x18002b5fc  inc     esi
0x18002b5fe  cmp     esi, [rdi+8]
0x18002b601  jb      loc_18002B57D
0x18002b607  test    ebx, ebx
0x18002b609  js      loc_18002B6D2
0x18002b60f  mov     word ptr [rdi], 101Fh
0x18002b614  mov     ebx, r12d
0x18002b617  jmp     loc_18002B6D2
0x18002b61c  cmp     [rdi+10h], r12
0x18002b620  jz      loc_18002B6CD
0x18002b626  mov     esi, r12d
0x18002b629  cmp     [rdi+8], r12d
0x18002b62d  jbe     loc_18002B6D2
0x18002b633  test    ebx, ebx
0x18002b635  js      loc_18002B6D2
0x18002b63b  mov     eax, esi
0x18002b63d  lea     rcx, [rax+rax*2]
0x18002b641  mov     rax, [rdi+10h]
0x18002b645  lea     rcx, [rax+rcx*8]; this
0x18002b649  mov     edx, r15d; struct tagPROPVARIANT *
0x18002b64c  call    ?PropVariantConvertStrToWStr@PropvarCvt@@YAJPEAUtagPROPVARIANT@@I@Z; PropvarCvt::PropVariantConvertStrToWStr(tagPROPVARIANT *,uint)
0x18002b651  mov     ebx, eax
0x18002b653  inc     esi
0x18002b655  cmp     esi, [rdi+8]
0x18002b658  jb      short loc_18002B633
0x18002b65a  jmp     short loc_18002B6D2
0x18002b65c  mov     rdx, [rdi+8]; lpMultiByteStr
0x18002b660  test    rdx, rdx
0x18002b663  jz      short loc_18002B6CD
0x18002b665  mov     [rbp+pvar], r12
0x18002b669  lea     rax, [rbp+pvar]
0x18002b66d  mov     [rbp+pvarDest], rax
0x18002b671  mov     [rbp+pvarDest+8], r12
0x18002b675  mov     byte ptr [rbp+var_10], 1
0x18002b679  lea     r8, [rbp+pvarDest+8]
0x18002b67d  mov     ecx, r15d; CodePage
0x18002b680  call    CreateTaskMemWStrFromStr
0x18002b685  mov     ebx, eax
0x18002b687  lea     rcx, [rbp+pvarDest]
0x18002b68b  call    ??1?$out_param_t@V?$unique_ptr@_WU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<wchar_t,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<wchar_t,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x18002b690  test    ebx, ebx
0x18002b692  js      short loc_18002B6B8
0x18002b694  mov     rcx, rdi; pvar
0x18002b697  call    cs:__imp_PropVariantClear
0x18002b69d  mov     ebx, eax
0x18002b69f  test    eax, eax
0x18002b6a1  js      short loc_18002B6B8
0x18002b6a3  mov     word ptr [rdi], 1Fh
0x18002b6a8  mov     rax, [rbp+pvar]
0x18002b6ac  mov     rcx, r12
0x18002b6af  mov     [rdi+8], rax
0x18002b6b3  mov     ebx, r12d
0x18002b6b6  jmp     short loc_18002B6BC
0x18002b6b8  mov     rcx, [rbp+pvar]; pv
0x18002b6bc  mov     [rbp+pvar], r12
0x18002b6c0  test    rcx, rcx
0x18002b6c3  jz      short loc_18002B6D2
0x18002b6c5  call    cs:__imp_CoTaskMemFree
0x18002b6cb  jmp     short loc_18002B6D2
0x18002b6cd  mov     ebx, 80004003h
0x18002b6d2  mov     eax, ebx
0x18002b6d4  lea     r11, [rsp+40h+var_s0]
0x18002b6d9  mov     rbx, [r11+38h]
0x18002b6dd  mov     rsi, [r11+40h]
0x18002b6e1  mov     rsp, r11
0x18002b6e4  pop     r15
0x18002b6e6  pop     r14
0x18002b6e8  pop     r12
0x18002b6ea  pop     rdi
0x18002b6eb  pop     rbp
0x18002b6ec  retn
```
