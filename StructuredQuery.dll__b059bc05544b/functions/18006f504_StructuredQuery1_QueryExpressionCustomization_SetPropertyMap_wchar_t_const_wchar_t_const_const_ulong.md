# StructuredQuery1::QueryExpressionCustomization::SetPropertyMap(wchar_t const *,wchar_t const * const *,ulong)

- ea: `0x18006f504`
- end: `0x18006f6bb`
- name: `?SetPropertyMap@QueryExpressionCustomization@StructuredQuery1@@QEAAJPEB_WPEBQEB_WK@Z`
- size: `439`
- prototype: `int(StructuredQuery1::QueryExpressionCustomization *__hidden this, const wchar_t *, const wchar_t *const *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800101b0`

## callees

- `0x1800094f8`
- `0x180020250`
- `0x18003bed0`
- `0x18004146c`
- `0x18005daf0`
- `0x18006da58`
- `0x18006f504`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006f5a6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006f5ec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006f5a6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006f5ec`

## pseudocode

```c
__int64 __fastcall StructuredQuery1::QueryExpressionCustomization::SetPropertyMap(
        StructuredQuery1::QueryExpressionCustomization *this,
        wchar_t *a2,
        const wchar_t **a3,
        unsigned int a4)
{
  unsigned __int64 v5; // r15
  int KeyFromConditionPropertyName; // edi
  __int64 v8; // r14
  void **v9; // rbx
  __int64 v10; // rdx
  unsigned int v11; // ecx
  unsigned int v12; // eax
  __int64 v13; // r9
  __int64 v14; // r14
  IMalloc *v15; // rcx
  struct _tagpropertykey *v16; // r8
  void **v17; // r9
  __int64 v18; // rsi
  int v19; // eax
  unsigned __int64 v21; // [rsp+20h] [rbp-38h] BYREF
  PROPERTYKEY v22; // [rsp+28h] [rbp-30h] BYREF

  v5 = a4;
  memset(&v22, 0, sizeof(v22));
  KeyFromConditionPropertyName = StructuredQuery1::GetKeyFromConditionPropertyName(
                                   a2,
                                   &v22,
                                   (struct _tagpropertykey *)a3);
  if ( KeyFromConditionPropertyName >= 0 )
  {
    if ( operator==((__int64)&v22, (__int64)&PKEY_Null) )
    {
      return (unsigned int)-2147024809;
    }
    else
    {
      v8 = 0;
      v9 = (void **)((char *)this + 32);
      while ( (unsigned int)v8 < *((_DWORD *)this + 11) )
      {
        v9 = (void **)((char *)this + 32);
        if ( operator==((__int64)&v22, *((_QWORD *)this + 4) + 40 * v8) )
        {
          CoTaskMemFree(*(LPVOID *)(v10 + 24));
          v11 = v8;
          *((_QWORD *)*v9 + 5 * v8 + 3) = 0;
          *((_DWORD *)*v9 + 10 * v8 + 8) = 0;
          goto LABEL_13;
        }
        v8 = (unsigned int)(v8 + 1);
      }
      v12 = *((_DWORD *)this + 11);
      if ( v12 == *((_DWORD *)this + 10) )
      {
        v21 = 0;
        KeyFromConditionPropertyName = StructuredQuery1::CoExtendArray<StructuredQuery1::VIRTUAL_PROPERTY_INFO>(
                                         *v9,
                                         v12);
        if ( KeyFromConditionPropertyName >= 0 )
        {
          CoTaskMemFree(*v9);
          *v9 = (void *)v21;
        }
      }
      *((PROPERTYKEY *)*v9 + 2 * *((unsigned int *)this + 11)) = v22;
      v11 = *((_DWORD *)this + 11);
      *((_DWORD *)this + 11) = v11 + 1;
LABEL_13:
      if ( (_DWORD)v5 )
      {
        v13 = (__int64)*v9 + 24;
        v21 = 0;
        v14 = 5LL * v11;
        *(_QWORD *)(v13 + 40LL * v11) = 0;
        KeyFromConditionPropertyName = ULongLongMult(v5, 0x14u, &v21);
        if ( KeyFromConditionPropertyName >= 0 )
          KeyFromConditionPropertyName = CTCoAllocPolicy::Alloc(v15, 1, v21, v17);
        if ( KeyFromConditionPropertyName >= 0 )
        {
          v18 = 0;
          *((_DWORD *)*v9 + 2 * v14 + 8) = v5;
          do
          {
            if ( (unsigned int)v18 >= (unsigned int)v5 )
              break;
            v19 = StructuredQuery1::GetKeyFromConditionPropertyName(
                    (wchar_t *)a3[v18],
                    (PROPERTYKEY *)(*((_QWORD *)*v9 + v14 + 3) + 20 * v18),
                    v16);
            v18 = (unsigned int)(v18 + 1);
            KeyFromConditionPropertyName = v19;
          }
          while ( v19 >= 0 );
        }
      }
    }
  }
  return (unsigned int)KeyFromConditionPropertyName;
}

```

## disassembly

```asm
0x18006f504  push    rbp
0x18006f506  push    rbx
0x18006f507  push    rsi
0x18006f508  push    rdi
0x18006f509  push    r12
0x18006f50b  push    r13
0x18006f50d  push    r14
0x18006f50f  push    r15
0x18006f511  mov     rbp, rsp
0x18006f514  sub     rsp, 58h
0x18006f518  mov     rax, cs:__security_cookie
0x18006f51f  xor     rax, rsp
0x18006f522  mov     [rbp+var_18], rax
0x18006f526  mov     rsi, rcx
0x18006f529  mov     r15d, r9d
0x18006f52c  xor     ecx, ecx
0x18006f52e  mov     rax, rdx
0x18006f531  mov     [rbp+var_20], ecx
0x18006f534  lea     rdx, [rbp+var_30]; wchar_t *
0x18006f538  xorps   xmm0, xmm0
0x18006f53b  mov     rcx, rax; Buffer
0x18006f53e  mov     r13, r8
0x18006f541  movups  xmmword ptr [rbp+var_30], xmm0
0x18006f545  call    ?GetKeyFromConditionPropertyName@StructuredQuery1@@YAJPEB_WPEAU_tagpropertykey@@@Z; StructuredQuery1::GetKeyFromConditionPropertyName(wchar_t const *,_tagpropertykey *)
0x18006f54a  mov     edi, eax
0x18006f54c  test    eax, eax
0x18006f54e  js      loc_18006F69C
0x18006f554  lea     rdx, PKEY_Null
0x18006f55b  lea     rcx, [rbp+var_30]
0x18006f55f  call    ??8@YAHAEBU_tagpropertykey@@0@Z; operator==(_tagpropertykey const &,_tagpropertykey const &)
0x18006f564  test    eax, eax
0x18006f566  jz      short loc_18006F572
0x18006f568  mov     edi, 80070057h
0x18006f56d  jmp     loc_18006F69C
0x18006f572  xor     r14d, r14d
0x18006f575  lea     rbx, [rsi+20h]
0x18006f579  xor     ecx, ecx
0x18006f57b  cmp     r14d, [rsi+2Ch]
0x18006f57f  jnb     short loc_18006F5C9
0x18006f581  lea     rbx, [rsi+20h]
0x18006f585  mov     rax, [rbx]
0x18006f588  lea     r12, [r14+r14*4]
0x18006f58c  lea     rcx, [rbp+var_30]
0x18006f590  lea     rdx, [rax+r12*8]
0x18006f594  call    ??8@YAHAEBU_tagpropertykey@@0@Z; operator==(_tagpropertykey const &,_tagpropertykey const &)
0x18006f599  test    eax, eax
0x18006f59b  jnz     short loc_18006F5A2
0x18006f59d  inc     r14d
0x18006f5a0  jmp     short loc_18006F579
0x18006f5a2  mov     rcx, [rdx+18h]; pv
0x18006f5a6  call    cs:__imp_CoTaskMemFree
0x18006f5ac  mov     rax, [rbx]
0x18006f5af  mov     ecx, r14d
0x18006f5b2  mov     qword ptr [rax+r12*8+18h], 0
0x18006f5bb  mov     rax, [rbx]
0x18006f5be  mov     dword ptr [rax+r12*8+20h], 0
0x18006f5c7  jmp     short loc_18006F61B
0x18006f5c9  mov     eax, [rsi+2Ch]
0x18006f5cc  cmp     eax, [rsi+28h]
0x18006f5cf  jnz     short loc_18006F5F9
0x18006f5d1  mov     [rbp+var_38], rcx
0x18006f5d5  lea     r9, [rbp+var_38]
0x18006f5d9  mov     rcx, [rbx]; Src
0x18006f5dc  mov     edx, eax; unsigned __int64
0x18006f5de  call    ??$CoExtendArray@UVIRTUAL_PROPERTY_INFO@StructuredQuery1@@@StructuredQuery1@@YAJPEBUVIRTUAL_PROPERTY_INFO@0@_K1PEAPEAU10@@Z; StructuredQuery1::CoExtendArray<StructuredQuery1::VIRTUAL_PROPERTY_INFO>(StructuredQuery1::VIRTUAL_PROPERTY_INFO const *,unsigned __int64,unsigned __int64,StructuredQuery1::VIRTUAL_PROPERTY_INFO * *)
0x18006f5e3  mov     edi, eax
0x18006f5e5  test    eax, eax
0x18006f5e7  js      short loc_18006F5F9
0x18006f5e9  mov     rcx, [rbx]; pv
0x18006f5ec  call    cs:__imp_CoTaskMemFree
0x18006f5f2  mov     rax, [rbp+var_38]
0x18006f5f6  mov     [rbx], rax
0x18006f5f9  mov     eax, [rsi+2Ch]
0x18006f5fc  mov     rcx, [rbx]
0x18006f5ff  movups  xmm0, xmmword ptr [rbp+var_30]
0x18006f603  lea     rdx, [rax+rax*4]
0x18006f607  movups  xmmword ptr [rcx+rdx*8], xmm0
0x18006f60b  mov     eax, [rbp+var_20]
0x18006f60e  mov     [rcx+rdx*8+10h], eax
0x18006f612  mov     ecx, [rsi+2Ch]
0x18006f615  lea     eax, [rcx+1]
0x18006f618  mov     [rsi+2Ch], eax
0x18006f61b  test    r15d, r15d
0x18006f61e  jz      short loc_18006F69C
0x18006f620  mov     r9, [rbx]
0x18006f623  lea     r8, [rbp+var_38]; unsigned __int64 *
0x18006f627  mov     eax, ecx
0x18006f629  add     r9, 18h
0x18006f62d  mov     rcx, r15; unsigned __int64
0x18006f630  mov     [rbp+var_38], 0
0x18006f638  mov     edx, 14h; unsigned __int64
0x18006f63d  lea     r14, [rax+rax*4]
0x18006f641  lea     r9, [r9+r14*8]
0x18006f645  mov     qword ptr [r9], 0
0x18006f64c  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18006f651  mov     edi, eax
0x18006f653  test    eax, eax
0x18006f655  js      short loc_18006F667
0x18006f657  mov     r8, [rbp+var_38]; unsigned __int64
0x18006f65b  mov     edx, 1; unsigned int
0x18006f660  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x18006f665  mov     edi, eax
0x18006f667  test    edi, edi
0x18006f669  js      short loc_18006F69C
0x18006f66b  mov     rax, [rbx]
0x18006f66e  xor     esi, esi
0x18006f670  mov     [rax+r14*8+20h], r15d
0x18006f675  cmp     esi, r15d
0x18006f678  jnb     short loc_18006F69C
0x18006f67a  mov     rax, [rbx]
0x18006f67d  lea     rdx, [rsi+rsi*4]
0x18006f681  mov     rcx, [r13+rsi*8+0]; Buffer
0x18006f686  mov     rax, [rax+r14*8+18h]
0x18006f68b  lea     rdx, [rax+rdx*4]; wchar_t *
0x18006f68f  call    ?GetKeyFromConditionPropertyName@StructuredQuery1@@YAJPEB_WPEAU_tagpropertykey@@@Z; StructuredQuery1::GetKeyFromConditionPropertyName(wchar_t const *,_tagpropertykey *)
0x18006f694  inc     esi
0x18006f696  mov     edi, eax
0x18006f698  test    eax, eax
0x18006f69a  jns     short loc_18006F675
0x18006f69c  mov     eax, edi
0x18006f69e  mov     rcx, [rbp+var_18]
0x18006f6a2  xor     rcx, rsp; StackCookie
0x18006f6a5  call    __security_check_cookie
0x18006f6aa  add     rsp, 58h
0x18006f6ae  pop     r15
0x18006f6b0  pop     r14
0x18006f6b2  pop     r13
0x18006f6b4  pop     r12
0x18006f6b6  pop     rdi
0x18006f6b7  pop     rsi
0x18006f6b8  pop     rbx
0x18006f6b9  pop     rbp
0x18006f6ba  retn
```
