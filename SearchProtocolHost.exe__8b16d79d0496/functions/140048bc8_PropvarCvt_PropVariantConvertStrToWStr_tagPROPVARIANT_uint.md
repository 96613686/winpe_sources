# PropvarCvt::PropVariantConvertStrToWStr(tagPROPVARIANT *,uint)

- ea: `0x140048bc8`
- end: `0x140048e6f`
- name: `?PropVariantConvertStrToWStr@PropvarCvt@@YAJPEAUtagPROPVARIANT@@I@Z`
- size: `679`
- prototype: `__int64 __fastcall(PropvarCvt *__hidden this, struct tagPROPVARIANT *, unsigned int)`
- caller_count: `3`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x140012c80`
- `0x14003c630`
- `0x140048bc8`

## callees

- `0x140047df4`
- `0x1400489c4`
- `0x140048b44`
- `0x140048bc8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140048c6b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140048c6b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x140048c88`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x140048cae`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x140048ce2`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x140048e1d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x140048c88`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x140048cae`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x140048ce2`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x140048e1d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140048cd1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140048d53`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140048d7e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140048e4d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140048cd1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140048d53`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140048d7e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140048e4d`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x140048c49`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x140048c49`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall PropvarCvt::PropVariantConvertStrToWStr(PropvarCvt *this, struct tagPROPVARIANT *a2)
{
  HRESULT TaskMemWStrFromStr; // edi
  unsigned int v5; // r8d
  __int64 v6; // rcx
  void *v7; // rcx
  unsigned int v8; // r8d
  PROPVARIANT *v9; // rbx
  __int64 v10; // rbx
  __int64 v11; // rdx
  LPVOID v12; // rcx
  __int64 i; // rbx
  __int64 v14; // rdx
  void *v15; // rcx
  PROPVARIANT pvarDest[2]; // [rsp+28h] [rbp-18h] BYREF
  void *v17; // [rsp+38h] [rbp-8h]
  LPVOID pv; // [rsp+60h] [rbp+20h] BYREF

  if ( !this )
    return 2147500035LL;
  TaskMemWStrFromStr = 0;
  if ( (unsigned int)PropVariantContainsStr(this, a2) )
  {
    v6 = (unsigned int)*(unsigned __int16 *)this - 30;
    if ( *(_WORD *)this == 30 )
    {
      v14 = *((_QWORD *)this + 1);
      if ( v14 )
      {
        pv = 0;
        pvarDest[0] = &pv;
        pvarDest[1] = 0;
        LOBYTE(v17) = 1;
        TaskMemWStrFromStr = CreateTaskMemWStrFromStr(v6, v14, &pvarDest[1]);
        wil::details::out_param_t<wistd::unique_ptr<wchar_t,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<wchar_t,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(pvarDest);
        if ( TaskMemWStrFromStr < 0
          || (TaskMemWStrFromStr = PropVariantClear((PROPVARIANT *)this), TaskMemWStrFromStr < 0) )
        {
          v15 = pv;
        }
        else
        {
          *(_WORD *)this = 31;
          v15 = 0;
          *((_QWORD *)this + 1) = pv;
          TaskMemWStrFromStr = 0;
        }
        pv = 0;
        if ( v15 )
          CoTaskMemFree(v15);
        return (unsigned int)TaskMemWStrFromStr;
      }
    }
    else if ( *(_WORD *)this == 4108 )
    {
      if ( *((_QWORD *)this + 2) )
      {
        for ( i = 0; (unsigned int)i < *((_DWORD *)this + 2); i = (unsigned int)(i + 1) )
        {
          if ( TaskMemWStrFromStr < 0 )
            break;
          TaskMemWStrFromStr = PropvarCvt::PropVariantConvertStrToWStr(
                                 (PropvarCvt *)(*((_QWORD *)this + 2) + 24 * i),
                                 0,
                                 v5);
        }
        return (unsigned int)TaskMemWStrFromStr;
      }
    }
    else
    {
      v7 = (void *)((unsigned int)*(unsigned __int16 *)this - 4126);
      if ( *(_WORD *)this != 4126 )
      {
        if ( *(_WORD *)this == 16396 )
        {
          *(_OWORD *)pvarDest = 0;
          v17 = 0;
          TaskMemWStrFromStr = PropVariantCopy(pvarDest, *((const PROPVARIANT **)this + 1));
          if ( TaskMemWStrFromStr >= 0 )
            TaskMemWStrFromStr = PropvarCvt::PropVariantConvertStrToWStr((PropvarCvt *)pvarDest, 0, v8);
          if ( TaskMemWStrFromStr >= 0 )
          {
            v9 = (PROPVARIANT *)CoTaskMemAlloc(0x18u);
            if ( v9 )
            {
              *(_OWORD *)v9 = 0;
              v9[2] = 0;
              TaskMemWStrFromStr = PropVariantClear(v9);
              if ( TaskMemWStrFromStr < 0
                || (*(_OWORD *)v9 = *(_OWORD *)pvarDest,
                    v9[2] = v17,
                    LOWORD(pvarDest[0]) = 0,
                    TaskMemWStrFromStr = PropVariantClear((PROPVARIANT *)this),
                    TaskMemWStrFromStr < 0) )
              {
                CoTaskMemFree(v9);
              }
              else
              {
                *(_WORD *)this = 4108;
                *((_DWORD *)this + 2) = 1;
                *((_QWORD *)this + 2) = v9;
                TaskMemWStrFromStr = 0;
              }
            }
            else
            {
              TaskMemWStrFromStr = -2147024882;
            }
          }
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
            v11 = *(_QWORD *)(*((_QWORD *)this + 2) + 8 * v10);
            if ( v11 )
            {
              pv = 0;
              pvarDest[0] = &pv;
              pvarDest[1] = 0;
              LOBYTE(v17) = 1;
              TaskMemWStrFromStr = CreateTaskMemWStrFromStr(v7, v11, &pvarDest[1]);
              wil::details::out_param_t<wistd::unique_ptr<wchar_t,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<wchar_t,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(pvarDest);
              if ( TaskMemWStrFromStr >= 0 )
              {
                CoTaskMemFree(*(LPVOID *)(*((_QWORD *)this + 2) + 8 * v10));
                v12 = pv;
                pv = 0;
                *(_QWORD *)(*((_QWORD *)this + 2) + 8 * v10) = v12;
              }
              v7 = pv;
              pv = 0;
              if ( v7 )
                CoTaskMemFree(v7);
            }
            else
            {
              TaskMemWStrFromStr = -2147467261;
            }
            v10 = (unsigned int)(v10 + 1);
            if ( (unsigned int)v10 >= *((_DWORD *)this + 2) )
            {
              if ( TaskMemWStrFromStr < 0 )
                return (unsigned int)TaskMemWStrFromStr;
              goto LABEL_29;
            }
          }
        }
        else
        {
LABEL_29:
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
0x140048bc8  push    rbp
0x140048bca  push    rdi
0x140048bcb  push    r14
0x140048bcd  mov     rbp, rsp
0x140048bd0  sub     rsp, 40h
0x140048bd4  mov     [rbp+var_20], 0FFFFFFFFFFFFFFFEh
0x140048bdc  mov     [rsp+40h+arg_8], rbx
0x140048be1  mov     [rsp+40h+arg_10], rsi
0x140048be6  mov     rsi, rcx
0x140048be9  test    rcx, rcx
0x140048bec  jnz     short loc_140048BF8
0x140048bee  mov     eax, 80004003h
0x140048bf3  jmp     loc_140048E5C
0x140048bf8  xor     edi, edi
0x140048bfa  call    PropVariantContainsStr
0x140048bff  test    eax, eax
0x140048c01  jz      loc_140048E5A
0x140048c07  movzx   ecx, word ptr [rsi]
0x140048c0a  sub     ecx, 1Eh
0x140048c0d  jz      loc_140048DE5
0x140048c13  sub     ecx, 0FEEh
0x140048c19  jz      loc_140048DAA
0x140048c1f  sub     ecx, 12h
0x140048c22  jz      loc_140048CED
0x140048c28  cmp     ecx, 2FEEh
0x140048c2e  jnz     loc_140048E5A
0x140048c34  xorps   xmm0, xmm0
0x140048c37  xor     eax, eax
0x140048c39  movups  xmmword ptr [rbp+pvarDest], xmm0
0x140048c3d  mov     [rbp+var_8], rax
0x140048c41  mov     rdx, [rsi+8]; pvarSrc
0x140048c45  lea     rcx, [rbp+pvarDest]; pvarDest
0x140048c49  call    cs:__imp_PropVariantCopy
0x140048c4f  mov     edi, eax
0x140048c51  test    eax, eax
0x140048c53  js      short loc_140048C62
0x140048c55  xor     edx, edx; struct tagPROPVARIANT *
0x140048c57  lea     rcx, [rbp+pvarDest]; this
0x140048c5b  call    ?PropVariantConvertStrToWStr@PropvarCvt@@YAJPEAUtagPROPVARIANT@@I@Z; PropvarCvt::PropVariantConvertStrToWStr(tagPROPVARIANT *,uint)
0x140048c60  mov     edi, eax
0x140048c62  test    edi, edi
0x140048c64  js      short loc_140048CDE
0x140048c66  mov     ecx, 18h; cb
0x140048c6b  call    cs:__imp_CoTaskMemAlloc
0x140048c71  mov     rbx, rax
0x140048c74  test    rax, rax
0x140048c77  jz      short loc_140048CD9
0x140048c79  xorps   xmm0, xmm0
0x140048c7c  xor     eax, eax
0x140048c7e  movups  xmmword ptr [rbx], xmm0
0x140048c81  mov     [rbx+10h], rax
0x140048c85  mov     rcx, rbx; pvar
0x140048c88  call    cs:__imp_PropVariantClear
0x140048c8e  mov     edi, eax
0x140048c90  test    eax, eax
0x140048c92  js      short loc_140048CCE
0x140048c94  movups  xmm0, xmmword ptr [rbp+pvarDest]
0x140048c98  movups  xmmword ptr [rbx], xmm0
0x140048c9b  movsd   xmm1, [rbp+var_8]
0x140048ca0  movsd   qword ptr [rbx+10h], xmm1
0x140048ca5  xor     eax, eax
0x140048ca7  mov     word ptr [rbp+pvarDest], ax
0x140048cab  mov     rcx, rsi; pvar
0x140048cae  call    cs:__imp_PropVariantClear
0x140048cb4  mov     edi, eax
0x140048cb6  test    eax, eax
0x140048cb8  js      short loc_140048CCE
0x140048cba  mov     word ptr [rsi], 100Ch
0x140048cbf  mov     dword ptr [rsi+8], 1
0x140048cc6  mov     [rsi+10h], rbx
0x140048cca  xor     edi, edi
0x140048ccc  jmp     short loc_140048CDE
0x140048cce  mov     rcx, rbx; pv
0x140048cd1  call    cs:__imp_CoTaskMemFree
0x140048cd7  jmp     short loc_140048CDE
0x140048cd9  mov     edi, 8007000Eh
0x140048cde  lea     rcx, [rbp+pvarDest]; pvar
0x140048ce2  call    cs:__imp_PropVariantClear
0x140048ce8  jmp     loc_140048E5A
0x140048ced  cmp     [rsi+10h], rdi
0x140048cf1  jz      loc_140048E55
0x140048cf7  xor     ebx, ebx
0x140048cf9  cmp     [rsi+8], ebx
0x140048cfc  jbe     loc_140048D9E
0x140048d02  test    edi, edi
0x140048d04  js      loc_140048E5A
0x140048d0a  mov     rax, [rsi+10h]
0x140048d0e  mov     rdx, [rax+rbx*8]
0x140048d12  test    rdx, rdx
0x140048d15  jz      short loc_140048D86
0x140048d17  mov     [rbp+pv], 0
0x140048d1f  lea     rax, [rbp+pv]
0x140048d23  mov     [rbp+pvarDest], rax
0x140048d27  mov     [rbp+pvarDest+8], 0
0x140048d2f  mov     byte ptr [rbp+var_8], 1
0x140048d33  lea     r8, [rbp+pvarDest+8]
0x140048d37  call    CreateTaskMemWStrFromStr
0x140048d3c  mov     edi, eax
0x140048d3e  lea     rcx, [rbp+pvarDest]
0x140048d42  call    ??1?$out_param_t@V?$unique_ptr@_WU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<wchar_t,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<wchar_t,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x140048d47  test    edi, edi
0x140048d49  js      short loc_140048D6D
0x140048d4b  mov     rcx, [rsi+10h]
0x140048d4f  mov     rcx, [rcx+rbx*8]; pv
0x140048d53  call    cs:__imp_CoTaskMemFree
0x140048d59  mov     rcx, [rbp+pv]
0x140048d5d  mov     [rbp+pv], 0
0x140048d65  mov     rax, [rsi+10h]
0x140048d69  mov     [rax+rbx*8], rcx
0x140048d6d  mov     rcx, [rbp+pv]; pv
0x140048d71  mov     [rbp+pv], 0
0x140048d79  test    rcx, rcx
0x140048d7c  jz      short loc_140048D8B
0x140048d7e  call    cs:__imp_CoTaskMemFree
0x140048d84  jmp     short loc_140048D8B
0x140048d86  mov     edi, 80004003h
0x140048d8b  inc     ebx
0x140048d8d  cmp     ebx, [rsi+8]
0x140048d90  jb      loc_140048D02
0x140048d96  test    edi, edi
0x140048d98  js      loc_140048E5A
0x140048d9e  mov     word ptr [rsi], 101Fh
0x140048da3  xor     edi, edi
0x140048da5  jmp     loc_140048E5A
0x140048daa  cmp     [rsi+10h], rdi
0x140048dae  jz      loc_140048E55
0x140048db4  xor     ebx, ebx
0x140048db6  cmp     [rsi+8], ebx
0x140048db9  jbe     loc_140048E5A
0x140048dbf  test    edi, edi
0x140048dc1  js      loc_140048E5A
0x140048dc7  lea     rcx, [rbx+rbx*2]
0x140048dcb  mov     rax, [rsi+10h]
0x140048dcf  lea     rcx, [rax+rcx*8]; this
0x140048dd3  xor     edx, edx; struct tagPROPVARIANT *
0x140048dd5  call    ?PropVariantConvertStrToWStr@PropvarCvt@@YAJPEAUtagPROPVARIANT@@I@Z; PropvarCvt::PropVariantConvertStrToWStr(tagPROPVARIANT *,uint)
0x140048dda  mov     edi, eax
0x140048ddc  inc     ebx
0x140048dde  cmp     ebx, [rsi+8]
0x140048de1  jb      short loc_140048DBF
0x140048de3  jmp     short loc_140048E5A
0x140048de5  mov     rdx, [rsi+8]
0x140048de9  test    rdx, rdx
0x140048dec  jz      short loc_140048E55
0x140048dee  mov     [rbp+pv], rdi
0x140048df2  lea     rax, [rbp+pv]
0x140048df6  mov     [rbp+pvarDest], rax
0x140048dfa  mov     [rbp+pvarDest+8], rdi
0x140048dfe  mov     byte ptr [rbp+var_8], 1
0x140048e02  lea     r8, [rbp+pvarDest+8]
0x140048e06  call    CreateTaskMemWStrFromStr
0x140048e0b  mov     edi, eax
0x140048e0d  lea     rcx, [rbp+pvarDest]
0x140048e11  call    ??1?$out_param_t@V?$unique_ptr@_WU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<wchar_t,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<wchar_t,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x140048e16  test    edi, edi
0x140048e18  js      short loc_140048E3C
0x140048e1a  mov     rcx, rsi; pvar
0x140048e1d  call    cs:__imp_PropVariantClear
0x140048e23  mov     edi, eax
0x140048e25  test    eax, eax
0x140048e27  js      short loc_140048E3C
0x140048e29  mov     word ptr [rsi], 1Fh
0x140048e2e  mov     rax, [rbp+pv]
0x140048e32  xor     ecx, ecx
0x140048e34  mov     [rsi+8], rax
0x140048e38  xor     edi, edi
0x140048e3a  jmp     short loc_140048E40
0x140048e3c  mov     rcx, [rbp+pv]; pv
0x140048e40  mov     [rbp+pv], 0
0x140048e48  test    rcx, rcx
0x140048e4b  jz      short loc_140048E5A
0x140048e4d  call    cs:__imp_CoTaskMemFree
0x140048e53  jmp     short loc_140048E5A
0x140048e55  mov     edi, 80004003h
0x140048e5a  mov     eax, edi
0x140048e5c  mov     rbx, [rsp+40h+arg_8]
0x140048e61  mov     rsi, [rsp+40h+arg_10]
0x140048e66  add     rsp, 40h
0x140048e6a  pop     r14
0x140048e6c  pop     rdi
0x140048e6d  pop     rbp
0x140048e6e  retn
```
