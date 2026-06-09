# FILTERS_CUSTOM_PROVIDER::CreateFilterEntry(INativeConfigurationElementCollection *,ABO_NODE *,INativeConfigurationElement *,int)

- ea: `0x180010560`
- end: `0x180010757`
- name: `?CreateFilterEntry@FILTERS_CUSTOM_PROVIDER@@AEAAJPEAVINativeConfigurationElementCollection@@PEAVABO_NODE@@PEAVINativeConfigurationElement@@H@Z`
- size: `503`
- prototype: `int(FILTERS_CUSTOM_PROVIDER *__hidden this, struct INativeConfigurationElementCollection *, struct ABO_NODE *, struct INativeConfigurationElement *, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180010f40`

## callees

- `0x180002990`
- `0x1800047b0`
- `0x180006e28`
- `0x18000a4e8`
- `0x18000fde4`
- `0x180010238`
- `0x180010560`
- `0x18002c010`

## import_xrefs

- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x1800105c4`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x1800105c4`

## pseudocode

```c
__int64 __fastcall FILTERS_CUSTOM_PROVIDER::CreateFilterEntry(
        struct INativeConfigurationElement **this,
        struct INativeConfigurationElementCollection *a2,
        struct ABO_NODE *a3,
        struct INativeConfigurationElement *a4,
        unsigned int a5)
{
  __int64 v5; // rax
  CUSTOM_PROPERTY_PROVIDER *v10; // rdi
  int v11; // ebx
  __int64 (__fastcall *v12)(struct INativeConfigurationElement *, const wchar_t *, const unsigned __int16 *, _QWORD); // rbx
  const unsigned __int16 *Str; // rax
  __int64 v14; // rax
  FILTER_CUSTOM_PROVIDER *v15; // rax
  struct CUSTOM_PROPERTY_PROVIDER *v16; // rax
  _QWORD v18[3]; // [rsp+30h] [rbp-18h] BYREF
  struct INativeConfigurationElement *v19; // [rsp+98h] [rbp+50h] BYREF

  v5 = *(_QWORD *)a2;
  v19 = 0;
  v18[0] = 0;
  v10 = 0;
  v11 = (*(__int64 (__fastcall **)(struct INativeConfigurationElementCollection *, const wchar_t *, struct INativeConfigurationElement **))(v5 + 48))(
          a2,
          L"filter",
          &v19);
  if ( v11 >= 0 )
  {
    v12 = *(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, const unsigned __int16 *, _QWORD))(*(_QWORD *)v19 + 128LL);
    Str = STRU::QueryStr((struct ABO_NODE *)((char *)a3 + 56));
    v11 = v12(v19, L"name", Str, 0);
    if ( v11 >= 0 )
    {
      if ( !a4 )
        goto LABEL_26;
      v11 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, _QWORD *, _QWORD, _QWORD))(*(_QWORD *)a4 + 64LL))(
              a4,
              L"preCondition",
              v18,
              0,
              0);
      if ( v11 >= 0 )
      {
        if ( !v18[0] )
          goto LABEL_26;
        v14 = -1;
        do
          ++v14;
        while ( *(_WORD *)(v18[0] + 2 * v14) );
        if ( !v14
          || (v11 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, _QWORD, _QWORD))(*(_QWORD *)v19 + 128LL))(
                      v19,
                      L"preCondition",
                      v18[0],
                      0),
              v11 >= 0) )
        {
LABEL_26:
          v11 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, _QWORD, _QWORD))(*(_QWORD *)v19 + 136LL))(
                  v19,
                  L"enabled",
                  a5,
                  0);
          if ( v11 >= 0 )
          {
            v11 = PROPERTY_BAG::DeleteEntry((struct ABO_NODE *)((char *)a3 + 184), 0x7FBu);
            if ( (int)(v11 + 0x80000000) < 0 || v11 == -2147024894 )
            {
              v15 = (FILTER_CUSTOM_PROVIDER *)operator new(0x28u);
              if ( v15
                && (v16 = FILTER_CUSTOM_PROVIDER::FILTER_CUSTOM_PROVIDER(v15, a3, v19, this[3]), (v10 = v16) != 0) )
              {
                v11 = ABO_NODE::AddProvider(a3, v16);
                if ( v11 >= 0 )
                {
                  v11 = ABO_NODE::MapNodeAndChildren(a3);
                  if ( v11 >= 0 )
                    v11 = (*(__int64 (__fastcall **)(struct INativeConfigurationElementCollection *, struct INativeConfigurationElement *, __int64, _QWORD))(*(_QWORD *)a2 + 56LL))(
                            a2,
                            v19,
                            0xFFFFFFFFLL,
                            0);
                }
              }
              else
              {
                v11 = -2147024888;
              }
            }
          }
        }
      }
    }
  }
  if ( v19 )
  {
    (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v19 + 16LL))(v19);
    v19 = 0;
  }
  if ( v10 )
    CUSTOM_PROPERTY_PROVIDER::DereferenceCustomProvider(v10);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180010560  push    rbp
0x180010562  push    rbx
0x180010563  push    rsi
0x180010564  push    rdi
0x180010565  push    r12
0x180010567  push    r13
0x180010569  push    r14
0x18001056b  push    r15
0x18001056d  mov     rbp, rsp
0x180010570  sub     rsp, 48h
0x180010574  mov     rax, [rdx]
0x180010577  mov     r15, rdx
0x18001057a  xor     r12d, r12d
0x18001057d  lea     rdx, aFilter; "filter"
0x180010584  mov     rsi, r8
0x180010587  mov     [rbp+arg_8], r12
0x18001058b  mov     r13, rcx
0x18001058e  mov     [rbp+var_18], r12
0x180010592  mov     rax, [rax+30h]
0x180010596  lea     r8, [rbp+arg_8]
0x18001059a  mov     rcx, r15
0x18001059d  mov     r14, r9
0x1800105a0  mov     edi, r12d
0x1800105a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800105a8  mov     ebx, eax
0x1800105aa  test    eax, eax
0x1800105ac  js      loc_18001071E
0x1800105b2  mov     rax, [rbp+arg_8]
0x1800105b6  mov     rcx, [rax]
0x1800105b9  mov     rbx, [rcx+80h]
0x1800105c0  lea     rcx, [rsi+38h]
0x1800105c4  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x1800105ca  mov     rcx, [rbp+arg_8]
0x1800105ce  lea     rdx, aName; "name"
0x1800105d5  mov     r8, rax
0x1800105d8  xor     r9d, r9d
0x1800105db  mov     rax, rbx
0x1800105de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800105e3  mov     ebx, eax
0x1800105e5  test    eax, eax
0x1800105e7  js      loc_18001071E
0x1800105ed  test    r14, r14
0x1800105f0  jz      short loc_180010661
0x1800105f2  mov     rax, [r14]
0x1800105f5  lea     r8, [rbp+var_18]
0x1800105f9  xor     r9d, r9d
0x1800105fc  mov     [rsp+48h+var_28], r12
0x180010601  lea     rdx, aPrecondition; "preCondition"
0x180010608  mov     rcx, r14
0x18001060b  mov     rax, [rax+40h]
0x18001060f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010614  mov     ebx, eax
0x180010616  test    eax, eax
0x180010618  js      loc_18001071E
0x18001061e  mov     r8, [rbp+var_18]
0x180010622  test    r8, r8
0x180010625  jz      short loc_180010661
0x180010627  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001062b  inc     rax
0x18001062e  cmp     [r8+rax*2], r12w
0x180010633  jnz     short loc_18001062B
0x180010635  test    rax, rax
0x180010638  jz      short loc_180010661
0x18001063a  mov     rcx, [rbp+arg_8]
0x18001063e  lea     rdx, aPrecondition; "preCondition"
0x180010645  xor     r9d, r9d
0x180010648  mov     rax, [rcx]
0x18001064b  mov     rax, [rax+80h]
0x180010652  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010657  mov     ebx, eax
0x180010659  test    eax, eax
0x18001065b  js      loc_18001071E
0x180010661  mov     rcx, [rbp+arg_8]
0x180010665  lea     rdx, aEnabled; "enabled"
0x18001066c  mov     r8d, [rbp+arg_20]
0x180010670  xor     r9d, r9d
0x180010673  mov     rax, [rcx]
0x180010676  mov     rax, [rax+88h]
0x18001067d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010682  mov     ebx, eax
0x180010684  test    eax, eax
0x180010686  js      loc_18001071E
0x18001068c  lea     rcx, [rsi+0B8h]; this
0x180010693  mov     edx, 7FBh; unsigned int
0x180010698  call    ?DeleteEntry@PROPERTY_BAG@@QEAAJK@Z; PROPERTY_BAG::DeleteEntry(ulong)
0x18001069d  mov     ecx, 80000000h
0x1800106a2  mov     ebx, eax
0x1800106a4  add     eax, ecx
0x1800106a6  test    ecx, eax
0x1800106a8  jnz     short loc_1800106B2
0x1800106aa  cmp     ebx, 80070002h
0x1800106b0  jnz     short loc_18001071E
0x1800106b2  mov     ecx, 28h ; '('; Size
0x1800106b7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800106bc  test    rax, rax
0x1800106bf  jz      short loc_180010719
0x1800106c1  mov     r9, [r13+18h]; struct INativeConfigurationElement *
0x1800106c5  mov     rdx, rsi; struct ABO_NODE *
0x1800106c8  mov     r8, [rbp+arg_8]; struct INativeConfigurationElement *
0x1800106cc  mov     rcx, rax; this
0x1800106cf  call    ??0FILTER_CUSTOM_PROVIDER@@QEAA@PEAVABO_NODE@@PEAVINativeConfigurationElement@@1@Z; FILTER_CUSTOM_PROVIDER::FILTER_CUSTOM_PROVIDER(ABO_NODE *,INativeConfigurationElement *,INativeConfigurationElement *)
0x1800106d4  mov     rdi, rax
0x1800106d7  test    rax, rax
0x1800106da  jz      short loc_180010719
0x1800106dc  mov     rdx, rax; struct CUSTOM_PROPERTY_PROVIDER *
0x1800106df  mov     rcx, rsi; this
0x1800106e2  call    ?AddProvider@ABO_NODE@@QEAAJPEAVCUSTOM_PROPERTY_PROVIDER@@@Z; ABO_NODE::AddProvider(CUSTOM_PROPERTY_PROVIDER *)
0x1800106e7  mov     ebx, eax
0x1800106e9  test    eax, eax
0x1800106eb  js      short loc_18001071E
0x1800106ed  mov     rcx, rsi; this
0x1800106f0  call    ?MapNodeAndChildren@ABO_NODE@@QEAAJXZ; ABO_NODE::MapNodeAndChildren(void)
0x1800106f5  mov     ebx, eax
0x1800106f7  test    eax, eax
0x1800106f9  js      short loc_18001071E
0x1800106fb  mov     rax, [r15]
0x1800106fe  xor     r9d, r9d
0x180010701  mov     rdx, [rbp+arg_8]
0x180010705  or      r8d, 0FFFFFFFFh
0x180010709  mov     rcx, r15
0x18001070c  mov     rax, [rax+38h]
0x180010710  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010715  mov     ebx, eax
0x180010717  jmp     short loc_18001071E
0x180010719  mov     ebx, 80070008h
0x18001071e  mov     rcx, [rbp+arg_8]
0x180010722  test    rcx, rcx
0x180010725  jz      short loc_180010737
0x180010727  mov     rax, [rcx]
0x18001072a  mov     rax, [rax+10h]
0x18001072e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010733  mov     [rbp+arg_8], r12
0x180010737  test    rdi, rdi
0x18001073a  jz      short loc_180010744
0x18001073c  mov     rcx, rdi; this
0x18001073f  call    ?DereferenceCustomProvider@CUSTOM_PROPERTY_PROVIDER@@QEAAXXZ; CUSTOM_PROPERTY_PROVIDER::DereferenceCustomProvider(void)
0x180010744  mov     eax, ebx
0x180010746  add     rsp, 48h
0x18001074a  pop     r15
0x18001074c  pop     r14
0x18001074e  pop     r13
0x180010750  pop     r12
0x180010752  pop     rdi
0x180010753  pop     rsi
0x180010754  pop     rbx
0x180010755  pop     rbp
0x180010756  retn
```
