# ResourceLoader6::SimpleResourceLoader::put_Option(ushort *,tagVARIANT)

- ea: `0x1800154a0`
- end: `0x180015723`
- name: `?put_Option@SimpleResourceLoader@ResourceLoader6@@UEAAJPEAGUtagVARIANT@@@Z`
- size: `643`
- prototype: `__int64 __fastcall(ResourceLoader6::SimpleResourceLoader *__hidden this, unsigned __int16 *, struct tagVARIANT *__struct_ptr)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x180009790`
- `0x180014f2c`
- `0x180014fd4`
- `0x1800154a0`
- `0x18001572c`
- `0x180015784`
- `0x1800159c0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180015557`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800155d8`
- `msvcrt!??3@YAXPEAX@Z` at `0x180015557`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800155d8`

## string_xrefs

- `0x1800154c8`: `BinaryPath`
- `0x1800154df`: `RegistryPath`
- `0x180015680`: `QuerySpellerLexiconPath`
- `0x1800156a8`: `ProofLexPath`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ResourceLoader6::SimpleResourceLoader::put_Option(
        ResourceLoader6::SimpleResourceLoader *this,
        unsigned __int16 *a2,
        struct tagVARIANT *a3)
{
  __int64 v6; // rcx
  __int64 v7; // rcx
  void *v8; // rdi
  __int64 j; // rbx
  __int64 result; // rax
  void *v11; // rdi
  __int64 i; // rbx
  __int64 v13; // rax
  char *v14; // rcx
  _com_error *v15; // rbx
  _com_error *v16; // [rsp+38h] [rbp-60h] BYREF
  __int128 v17; // [rsp+40h] [rbp-58h] BYREF
  __int64 v18; // [rsp+50h] [rbp-48h]
  __int128 v19; // [rsp+58h] [rbp-40h] BYREF
  __int64 v20; // [rsp+68h] [rbp-30h]
  void *retaddr; // [rsp+98h] [rbp+0h]

  if ( !a2 )
    return 2147942487LL;
  try
  {
    if ( !(unsigned int)CMN_CompareStringNoCaseW(a2, L"BinaryPath") && a3->vt == 8 )
    {
      v17 = 0;
      v18 = 0;
      ResourceLoader6::SimpleResourceLoader::ParsePathsInto(v6, a3->llVal, &v17);
      std::vector<std::wstring>::operator=((char *)this + 16, &v17);
      v11 = (void *)v17;
      if ( (_QWORD)v17 )
      {
        for ( i = v17; i != *((_QWORD *)&v17 + 1); i += 32 )
          std::wstring::`scalar deleting destructor'(i, 0);
        operator delete(v11);
        v17 = 0;
        v18 = 0;
      }
      goto LABEL_11;
    }
    if ( !(unsigned int)CMN_CompareStringNoCaseW(a2, L"RegistryPath") && a3->vt == 8 )
    {
      v19 = 0;
      v20 = 0;
      ResourceLoader6::SimpleResourceLoader::ParsePathsInto(v7, a3->llVal, &v19);
      std::vector<std::wstring>::operator=((char *)this + 40, &v19);
      v8 = (void *)v19;
      if ( (_QWORD)v19 )
      {
        for ( j = v19; j != *((_QWORD *)&v19 + 1); j += 32 )
          std::wstring::`scalar deleting destructor'(j, 0);
        operator delete(v8);
        v19 = 0;
        v20 = 0;
      }
      goto LABEL_11;
    }
    if ( !(unsigned int)CMN_CompareStringNoCaseW(a2, L"CustomDict") && a3->vt == 8 )
    {
      v13 = std::char_traits<unsigned short>::length(a3->llVal);
      v14 = (char *)this + 72;
LABEL_34:
      std::wstring::assign(v14, a3->llVal, v13);
      goto LABEL_11;
    }
    if ( (unsigned int)CMN_CompareStringNoCaseW(a2, L"QuerySpeller") || a3->vt != 11 )
    {
      if ( (unsigned int)CMN_CompareStringNoCaseW(a2, L"IsPreReform") || a3->vt != 11 )
      {
        if ( (unsigned int)CMN_CompareStringNoCaseW(a2, L"QuerySpellerLexiconPath") || a3->vt != 8 )
        {
          if ( (unsigned int)CMN_CompareStringNoCaseW(a2, L"ProofLexPath") || a3->vt != 8 )
          {
            if ( !(unsigned int)CMN_CompareStringNoCaseW(a2, L"Locale") && a3->vt == 3 )
              *((_WORD *)this + 34) = a3->iVal;
            goto LABEL_11;
          }
          v13 = std::char_traits<unsigned short>::length(a3->llVal);
          v14 = (char *)this + 144;
        }
        else
        {
          v13 = std::char_traits<unsigned short>::length(a3->llVal);
          v14 = (char *)this + 112;
        }
        goto LABEL_34;
      }
      *((_BYTE *)this + 106) = a3->iVal != 0;
      *((_BYTE *)this + 107) = 1;
    }
    else
    {
      *((_BYTE *)this + 104) = a3->iVal != 0;
      *((_BYTE *)this + 105) = 1;
    }
LABEL_11:
    result = 0;
  }
  catch ( _com_error *v16 )
  {
    v15 = v16;
    ImxTraceCatch(1, *((unsigned int *)v16 + 2), retaddr);
    return *((unsigned int *)v15 + 2);
  }
  catch ( exception )
  {
    ImxTraceCatch(2, 2147500037LL, retaddr);
    return 2147500037LL;
  }
  if ( !(unsigned int)CMN_CompareStringNoCaseW(a2, L"BinaryPath") && a3->vt == 8 )
  {
    v17 = 0;
    v18 = 0;
    ResourceLoader6::SimpleResourceLoader::ParsePathsInto(v6, a3->llVal, &v17);
    std::vector<std::wstring>::operator=((char *)this + 16, &v17);
    v11 = (void *)v17;
    if ( (_QWORD)v17 )
    {
      for ( i = v17; i != *((_QWORD *)&v17 + 1); i += 32 )
        std::wstring::`scalar deleting destructor'(i, 0);
      operator delete(v11);
      v17 = 0;
      v18 = 0;
    }
    goto LABEL_11;
  }
}

```

## disassembly

```asm
0x1800154a0  push    rbx
0x1800154a2  push    rsi
0x1800154a3  push    rdi
0x1800154a4  push    r14
0x1800154a6  sub     rsp, 78h
0x1800154aa  mov     [rsp+98h+var_68], 0FFFFFFFFFFFFFFFEh
0x1800154b3  mov     rbx, r8
0x1800154b6  mov     rsi, rdx
0x1800154b9  mov     rdi, rcx
0x1800154bc  xor     r14d, r14d
0x1800154bf  test    rdx, rdx
0x1800154c2  jz      loc_1800155F1
0x1800154c8  lea     rdx, aBinarypath; "BinaryPath"
0x1800154cf  mov     rcx, rsi
0x1800154d2  call    CMN_CompareStringNoCaseW
0x1800154d7  test    eax, eax
0x1800154d9  jz      loc_180015577
0x1800154df  lea     rdx, aRegistrypath; "RegistryPath"
0x1800154e6  mov     rcx, rsi
0x1800154e9  call    CMN_CompareStringNoCaseW
0x1800154ee  test    eax, eax
0x1800154f0  jnz     loc_1800155FB
0x1800154f6  cmp     word ptr [rbx], 8
0x1800154fa  jnz     loc_1800155FB
0x180015500  xorps   xmm0, xmm0
0x180015503  movdqu  [rsp+98h+var_40], xmm0
0x180015509  mov     [rsp+98h+var_30], r14
0x18001550e  lea     r8, [rsp+98h+var_40]
0x180015513  mov     rdx, [rbx+8]
0x180015517  call    ?ParsePathsInto@SimpleResourceLoader@ResourceLoader6@@IEAAXPEBGAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; ResourceLoader6::SimpleResourceLoader::ParsePathsInto(ushort const *,std::vector<std::wstring> &)
0x18001551c  lea     rcx, [rdi+28h]
0x180015520  lea     rdx, [rsp+98h+var_40]
0x180015525  call    ??4?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAAEAV01@AEBV01@@Z; std::vector<std::wstring>::operator=(std::vector<std::wstring> const &)
0x18001552a  nop
0x18001552b  mov     rdi, qword ptr [rsp+98h+var_40]
0x180015530  test    rdi, rdi
0x180015533  jz      short loc_18001556B
0x180015535  mov     rbx, rdi
0x180015538  mov     [rsp+98h+var_70], rbx
0x18001553d  cmp     rbx, qword ptr [rsp+98h+var_40+8]
0x180015542  jz      short loc_180015554
0x180015544  xor     edx, edx
0x180015546  mov     rcx, rbx
0x180015549  call    ??_G?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAPEAXI@Z; std::wstring::`scalar deleting destructor'(uint)
0x18001554e  add     rbx, 20h ; ' '
0x180015552  jmp     short loc_180015538
0x180015554  mov     rcx, rdi
0x180015557  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001555d  xorps   xmm0, xmm0
0x180015560  movdqu  [rsp+98h+var_40], xmm0
0x180015566  mov     [rsp+98h+var_30], r14
0x18001556b  xor     eax, eax
0x18001556d  add     rsp, 78h
0x180015571  pop     r14
0x180015573  pop     rdi
0x180015574  pop     rsi
0x180015575  pop     rbx
0x180015576  retn
0x180015577  cmp     word ptr [rbx], 8
0x18001557b  jnz     loc_1800154DF
0x180015581  xorps   xmm0, xmm0
0x180015584  movdqu  [rsp+98h+var_58], xmm0
0x18001558a  mov     [rsp+98h+var_48], r14
0x18001558f  lea     r8, [rsp+98h+var_58]
0x180015594  mov     rdx, [rbx+8]
0x180015598  call    ?ParsePathsInto@SimpleResourceLoader@ResourceLoader6@@IEAAXPEBGAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; ResourceLoader6::SimpleResourceLoader::ParsePathsInto(ushort const *,std::vector<std::wstring> &)
0x18001559d  lea     rcx, [rdi+10h]
0x1800155a1  lea     rdx, [rsp+98h+var_58]
0x1800155a6  call    ??4?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAAEAV01@AEBV01@@Z; std::vector<std::wstring>::operator=(std::vector<std::wstring> const &)
0x1800155ab  nop
0x1800155ac  mov     rdi, qword ptr [rsp+98h+var_58]
0x1800155b1  test    rdi, rdi
0x1800155b4  jz      short loc_18001556B
0x1800155b6  mov     rbx, rdi
0x1800155b9  mov     [rsp+98h+var_78], rbx
0x1800155be  cmp     rbx, qword ptr [rsp+98h+var_58+8]
0x1800155c3  jz      short loc_1800155D5
0x1800155c5  xor     edx, edx
0x1800155c7  mov     rcx, rbx
0x1800155ca  call    ??_G?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAPEAXI@Z; std::wstring::`scalar deleting destructor'(uint)
0x1800155cf  add     rbx, 20h ; ' '
0x1800155d3  jmp     short loc_1800155B9
0x1800155d5  mov     rcx, rdi
0x1800155d8  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800155de  xorps   xmm0, xmm0
0x1800155e1  movdqu  [rsp+98h+var_58], xmm0
0x1800155e7  mov     [rsp+98h+var_48], r14
0x1800155ec  jmp     loc_18001556B
0x1800155f1  mov     eax, 80070057h
0x1800155f6  jmp     loc_18001556D
0x1800155fb  lea     rdx, aCustomdict; "CustomDict"
0x180015602  mov     rcx, rsi
0x180015605  call    CMN_CompareStringNoCaseW
0x18001560a  test    eax, eax
0x18001560c  jnz     short loc_180015626
0x18001560e  cmp     word ptr [rbx], 8
0x180015612  jnz     short loc_180015626
0x180015614  mov     rcx, [rbx+8]
0x180015618  call    ?length@?$char_traits@G@std@@SA_KPEBG@Z; std::char_traits<ushort>::length(ushort const *)
0x18001561d  lea     rcx, [rdi+48h]
0x180015621  jmp     loc_1800156D1
0x180015626  lea     rdx, aQueryspeller; "QuerySpeller"
0x18001562d  mov     rcx, rsi
0x180015630  call    CMN_CompareStringNoCaseW
0x180015635  test    eax, eax
0x180015637  jnz     short loc_180015653
0x180015639  cmp     word ptr [rbx], 0Bh
0x18001563d  jnz     short loc_180015653
0x18001563f  cmp     [rbx+8], r14w
0x180015644  setnz   al
0x180015647  mov     [rdi+68h], al
0x18001564a  mov     byte ptr [rdi+69h], 1
0x18001564e  jmp     loc_18001556B
0x180015653  lea     rdx, aIsprereform; "IsPreReform"
0x18001565a  mov     rcx, rsi
0x18001565d  call    CMN_CompareStringNoCaseW
0x180015662  test    eax, eax
0x180015664  jnz     short loc_180015680
0x180015666  cmp     word ptr [rbx], 0Bh
0x18001566a  jnz     short loc_180015680
0x18001566c  cmp     [rbx+8], r14w
0x180015671  setnz   al
0x180015674  mov     [rdi+6Ah], al
0x180015677  mov     byte ptr [rdi+6Bh], 1
0x18001567b  jmp     loc_18001556B
0x180015680  lea     rdx, aQueryspellerle; "QuerySpellerLexiconPath"
0x180015687  mov     rcx, rsi
0x18001568a  call    CMN_CompareStringNoCaseW
0x18001568f  test    eax, eax
0x180015691  jnz     short loc_1800156A8
0x180015693  cmp     word ptr [rbx], 8
0x180015697  jnz     short loc_1800156A8
0x180015699  mov     rcx, [rbx+8]
0x18001569d  call    ?length@?$char_traits@G@std@@SA_KPEBG@Z; std::char_traits<ushort>::length(ushort const *)
0x1800156a2  lea     rcx, [rdi+70h]
0x1800156a6  jmp     short loc_1800156D1
0x1800156a8  lea     rdx, aProoflexpath; "ProofLexPath"
0x1800156af  mov     rcx, rsi
0x1800156b2  call    CMN_CompareStringNoCaseW
0x1800156b7  test    eax, eax
0x1800156b9  jnz     short loc_1800156E2
0x1800156bb  cmp     word ptr [rbx], 8
0x1800156bf  jnz     short loc_1800156E2
0x1800156c1  mov     rcx, [rbx+8]
0x1800156c5  call    ?length@?$char_traits@G@std@@SA_KPEBG@Z; std::char_traits<ushort>::length(ushort const *)
0x1800156ca  lea     rcx, [rdi+90h]
0x1800156d1  mov     r8, rax
0x1800156d4  mov     rdx, [rbx+8]
0x1800156d8  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x1800156dd  jmp     loc_18001556B
0x1800156e2  lea     rdx, aLocale; "Locale"
0x1800156e9  mov     rcx, rsi
0x1800156ec  call    CMN_CompareStringNoCaseW
0x1800156f1  test    eax, eax
0x1800156f3  jnz     loc_18001556B
0x1800156f9  cmp     word ptr [rbx], 3
0x1800156fd  jnz     loc_18001556B
0x180015703  movzx   eax, word ptr [rbx+8]
0x180015707  mov     [rdi+44h], ax
0x18001570b  jmp     loc_18001556B
0x180015710  mov     eax, [rsp+98h+arg_8]
0x180015717  jmp     short loc_18001571E
0x180015719  mov     eax, 80004005h
0x18001571e  jmp     loc_18001556D
```
