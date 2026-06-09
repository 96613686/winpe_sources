# CONFIG_SECTION_DEFINITION_HELPER::RecursivelyAddSectionDefinitions(IAppHostSectionGroup *,ushort const *,IIS_CONFIG_SECTION_DEFINITION * const,ulong,int)

- ea: `0x18002e76c`
- end: `0x18002e9a5`
- name: `?RecursivelyAddSectionDefinitions@CONFIG_SECTION_DEFINITION_HELPER@@CAJPEAUIAppHostSectionGroup@@PEBGQEAUIIS_CONFIG_SECTION_DEFINITION@@KH@Z`
- size: `569`
- prototype: `__int64 __fastcall(struct IAppHostSectionGroup *, const unsigned __int16 *, struct IIS_CONFIG_SECTION_DEFINITION *const, unsigned int, int)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18001d8c0`
- `0x18002e76c`

## callees

- `0x180001fb0`
- `0x18002e558`
- `0x18002e69c`
- `0x18002e720`
- `0x18002e76c`
- `0x180034d00`
- `0x180036010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18002e887`
- `OLEAUT32!__imp_SysAllocString` at `0x18002e8e5`
- `OLEAUT32!__imp_SysAllocString` at `0x18002e887`
- `OLEAUT32!__imp_SysAllocString` at `0x18002e8e5`
- `OLEAUT32!__imp_SysFreeString` at `0x18002e90e`
- `OLEAUT32!__imp_SysFreeString` at `0x18002e90e`
- `OLEAUT32!__imp_VariantInit` at `0x18002e874`
- `OLEAUT32!__imp_VariantInit` at `0x18002e874`
- `OLEAUT32!__imp_VariantClear` at `0x18002e8cf`
- `OLEAUT32!__imp_VariantClear` at `0x18002e8cf`

## pseudocode

```c
__int64 __fastcall CONFIG_SECTION_DEFINITION_HELPER::RecursivelyAddSectionDefinitions(
        struct IAppHostSectionGroup *a1,
        const unsigned __int16 *a2,
        struct IIS_CONFIG_SECTION_DEFINITION *const a3,
        __int64 a4,
        int a5)
{
  int NextSectionGroupName; // ebx
  int i; // edi
  int v10; // eax
  HRESULT (__stdcall *get_Item)(IAppHostSectionGroup *, VARIANT, IAppHostSectionGroup **); // rax
  BSTR v12; // rax
  OLECHAR *v13; // rsi
  struct IAppHostSectionDefinitionCollection *v15; // [rsp+30h] [rbp-61h] BYREF
  struct IAppHostSectionGroup *v16; // [rsp+38h] [rbp-59h] BYREF
  VARIANTARG pvarg; // [rsp+40h] [rbp-51h] BYREF
  VARIANTARG v18; // [rsp+60h] [rbp-31h] BYREF
  _QWORD v19[4]; // [rsp+80h] [rbp-11h] BYREF
  OLECHAR *psz; // [rsp+A0h] [rbp+Fh]
  int v21; // [rsp+A8h] [rbp+17h]
  __int16 v22; // [rsp+ACh] [rbp+1Bh]
  int v23; // [rsp+B0h] [rbp+1Fh]

  v16 = 0;
  v19[0] = 0;
  v15 = 0;
  psz = (OLECHAR *)v19;
  v21 = 32;
  v22 = 256;
  v23 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  NextSectionGroupName = CONFIG_SECTION_DEFINITION_HELPER::GetNextSectionGroupName(a2, (struct STRU *)v19);
  if ( NextSectionGroupName < 0 )
    goto LABEL_19;
  if ( v23 )
  {
    VariantInit(&pvarg);
    pvarg.vt = 8;
    pvarg.llVal = (LONGLONG)SysAllocString(psz);
    if ( !pvarg.llVal )
      goto LABEL_13;
    get_Item = a1->lpVtbl->get_Item;
    v18 = pvarg;
    NextSectionGroupName = ((__int64 (__fastcall *)(struct IAppHostSectionGroup *, VARIANTARG *, struct IAppHostSectionGroup **))get_Item)(
                             a1,
                             &v18,
                             &v16);
    VariantClear(&pvarg);
    if ( NextSectionGroupName < 0 )
    {
      if ( NextSectionGroupName != -2147023483 )
        goto LABEL_19;
      v12 = SysAllocString(psz);
      v13 = v12;
      if ( !v12 )
      {
LABEL_13:
        NextSectionGroupName = -2147024882;
        goto LABEL_19;
      }
      NextSectionGroupName = ((__int64 (__fastcall *)(struct IAppHostSectionGroup *, BSTR, struct IAppHostSectionGroup **))a1->lpVtbl->AddSectionGroup)(
                               a1,
                               v12,
                               &v16);
      SysFreeString(v13);
      if ( NextSectionGroupName < 0 )
        goto LABEL_19;
    }
    NextSectionGroupName = CONFIG_SECTION_DEFINITION_HELPER::RecursivelyAddSectionDefinitions(
                             v16,
                             &a2[v23 + 1],
                             a3,
                             1u,
                             a5);
    goto LABEL_19;
  }
  NextSectionGroupName = ((__int64 (__fastcall *)(struct IAppHostSectionGroup *, struct IAppHostSectionDefinitionCollection **))a1->lpVtbl->get_Sections)(
                           a1,
                           &v15);
  if ( NextSectionGroupName >= 0 )
  {
    for ( i = 0; !i; i = 1 )
    {
      v10 = CONFIG_SECTION_DEFINITION_HELPER::AddOneConfigSectionDefinition(v15, a3);
      NextSectionGroupName = v10;
      if ( a5 == 1 && v10 == -2147024713 )
      {
        NextSectionGroupName = CONFIG_SECTION_DEFINITION_HELPER::DeleteOneConfigSectionDefinition(v15, a3);
        if ( NextSectionGroupName < 0 )
          break;
        v10 = CONFIG_SECTION_DEFINITION_HELPER::AddOneConfigSectionDefinition(v15, a3);
        NextSectionGroupName = v10;
      }
      if ( v10 < 0 )
        break;
    }
  }
LABEL_19:
  if ( v15 )
  {
    ((void (__fastcall *)(struct IAppHostSectionDefinitionCollection *))v15->lpVtbl->Release)(v15);
    v15 = 0;
  }
  if ( v16 )
  {
    ((void (__fastcall *)(struct IAppHostSectionGroup *))v16->lpVtbl->Release)(v16);
    v16 = 0;
  }
  BUFFER::~BUFFER((BUFFER *)v19);
  return (unsigned int)NextSectionGroupName;
}

```

## disassembly

```asm
0x18002e76c  mov     [rsp-8+arg_18], rbx
0x18002e771  push    rbp
0x18002e772  push    rsi
0x18002e773  push    rdi
0x18002e774  push    r14
0x18002e776  push    r15
0x18002e778  lea     rbp, [rsp-2Fh]
0x18002e77d  sub     rsp, 0C0h
0x18002e784  mov     rax, cs:__security_cookie
0x18002e78b  xor     rax, rsp
0x18002e78e  mov     [rbp+4Fh+var_28], rax
0x18002e792  xor     eax, eax
0x18002e794  mov     [rbp+4Fh+var_A8], 0
0x18002e79c  mov     r14, rdx
0x18002e79f  mov     qword ptr [rbp+4Fh+pvarg+10h], rax
0x18002e7a3  mov     [rbp+4Fh+var_60], rax
0x18002e7a7  lea     rdx, [rbp+4Fh+var_60]; this
0x18002e7ab  lea     rax, [rbp+4Fh+var_60]
0x18002e7af  mov     [rbp+4Fh+var_B0], 0
0x18002e7b7  mov     rdi, rcx
0x18002e7ba  mov     [rbp+4Fh+psz], rax
0x18002e7be  xorps   xmm0, xmm0
0x18002e7c1  mov     [rbp+4Fh+var_38], 20h ; ' '
0x18002e7c8  mov     rcx, r14; unsigned __int16 *
0x18002e7cb  mov     [rbp+4Fh+var_34], 100h
0x18002e7d1  mov     r15, r8
0x18002e7d4  mov     [rbp+4Fh+var_30], 0
0x18002e7db  movups  xmmword ptr [rbp+4Fh+pvarg], xmm0
0x18002e7df  call    ?GetNextSectionGroupName@CONFIG_SECTION_DEFINITION_HELPER@@CAJPEBGPEAVSTRU@@@Z; CONFIG_SECTION_DEFINITION_HELPER::GetNextSectionGroupName(ushort const *,STRU *)
0x18002e7e4  mov     ebx, eax
0x18002e7e6  test    eax, eax
0x18002e7e8  js      loc_18002E93D
0x18002e7ee  cmp     [rbp+4Fh+var_30], 0
0x18002e7f2  jnz     short loc_18002E870
0x18002e7f4  mov     rax, [rdi]
0x18002e7f7  lea     rdx, [rbp+4Fh+var_B0]
0x18002e7fb  mov     rcx, rdi
0x18002e7fe  mov     rax, [rax+28h]
0x18002e802  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e807  mov     ebx, eax
0x18002e809  test    eax, eax
0x18002e80b  js      loc_18002E93D
0x18002e811  xor     edi, edi
0x18002e813  cmp     edi, 1
0x18002e816  jnb     loc_18002E93D
0x18002e81c  mov     rcx, [rbp+4Fh+var_B0]; struct IAppHostSectionDefinitionCollection *
0x18002e820  mov     esi, edi
0x18002e822  shl     rsi, 5
0x18002e826  add     rsi, r15
0x18002e829  mov     rdx, rsi; struct IIS_CONFIG_SECTION_DEFINITION *
0x18002e82c  call    ?AddOneConfigSectionDefinition@CONFIG_SECTION_DEFINITION_HELPER@@CAJPEAUIAppHostSectionDefinitionCollection@@PEAUIIS_CONFIG_SECTION_DEFINITION@@@Z; CONFIG_SECTION_DEFINITION_HELPER::AddOneConfigSectionDefinition(IAppHostSectionDefinitionCollection *,IIS_CONFIG_SECTION_DEFINITION *)
0x18002e831  cmp     [rbp+4Fh+arg_20], 1
0x18002e835  mov     ebx, eax
0x18002e837  jnz     short loc_18002E864
0x18002e839  cmp     eax, 800700B7h
0x18002e83e  jnz     short loc_18002E864
0x18002e840  mov     rcx, [rbp+4Fh+var_B0]; struct IAppHostSectionDefinitionCollection *
0x18002e844  mov     rdx, rsi; struct IIS_CONFIG_SECTION_DEFINITION *
0x18002e847  call    ?DeleteOneConfigSectionDefinition@CONFIG_SECTION_DEFINITION_HELPER@@CAJPEAUIAppHostSectionDefinitionCollection@@PEAUIIS_CONFIG_SECTION_DEFINITION@@@Z; CONFIG_SECTION_DEFINITION_HELPER::DeleteOneConfigSectionDefinition(IAppHostSectionDefinitionCollection *,IIS_CONFIG_SECTION_DEFINITION *)
0x18002e84c  mov     ebx, eax
0x18002e84e  test    eax, eax
0x18002e850  js      loc_18002E93D
0x18002e856  mov     rcx, [rbp+4Fh+var_B0]; struct IAppHostSectionDefinitionCollection *
0x18002e85a  mov     rdx, rsi; struct IIS_CONFIG_SECTION_DEFINITION *
0x18002e85d  call    ?AddOneConfigSectionDefinition@CONFIG_SECTION_DEFINITION_HELPER@@CAJPEAUIAppHostSectionDefinitionCollection@@PEAUIIS_CONFIG_SECTION_DEFINITION@@@Z; CONFIG_SECTION_DEFINITION_HELPER::AddOneConfigSectionDefinition(IAppHostSectionDefinitionCollection *,IIS_CONFIG_SECTION_DEFINITION *)
0x18002e862  mov     ebx, eax
0x18002e864  test    eax, eax
0x18002e866  js      loc_18002E93D
0x18002e86c  inc     edi
0x18002e86e  jmp     short loc_18002E813
0x18002e870  lea     rcx, [rbp+4Fh+pvarg]; pvarg
0x18002e874  call    cs:__imp_VariantInit
0x18002e87a  mov     rcx, [rbp+4Fh+psz]; psz
0x18002e87e  mov     eax, 8
0x18002e883  mov     word ptr [rbp+4Fh+pvarg], ax
0x18002e887  call    cs:__imp_SysAllocString
0x18002e88d  mov     qword ptr [rbp+4Fh+pvarg+8], rax
0x18002e891  test    rax, rax
0x18002e894  jnz     short loc_18002E8A0
0x18002e896  mov     ebx, 8007000Eh
0x18002e89b  jmp     loc_18002E93D
0x18002e8a0  mov     rax, [rdi]
0x18002e8a3  lea     r8, [rbp+4Fh+var_A8]
0x18002e8a7  movups  xmm0, xmmword ptr [rbp+4Fh+pvarg]
0x18002e8ab  lea     rdx, [rbp+4Fh+var_80]
0x18002e8af  mov     rcx, rdi
0x18002e8b2  movsd   xmm1, qword ptr [rbp+4Fh+pvarg+10h]
0x18002e8b7  mov     rax, [rax+20h]
0x18002e8bb  movaps  [rbp+4Fh+var_80], xmm0
0x18002e8bf  movsd   [rbp+4Fh+var_70], xmm1
0x18002e8c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e8c9  lea     rcx, [rbp+4Fh+pvarg]; pvarg
0x18002e8cd  mov     ebx, eax
0x18002e8cf  call    cs:__imp_VariantClear
0x18002e8d5  test    ebx, ebx
0x18002e8d7  jns     short loc_18002E918
0x18002e8d9  cmp     ebx, 80070585h
0x18002e8df  jnz     short loc_18002E93D
0x18002e8e1  mov     rcx, [rbp+4Fh+psz]; psz
0x18002e8e5  call    cs:__imp_SysAllocString
0x18002e8eb  mov     rsi, rax
0x18002e8ee  test    rax, rax
0x18002e8f1  jz      short loc_18002E896
0x18002e8f3  mov     rax, [rdi]
0x18002e8f6  lea     r8, [rbp+4Fh+var_A8]
0x18002e8fa  mov     rdx, rsi
0x18002e8fd  mov     rcx, rdi
0x18002e900  mov     rax, [rax+30h]
0x18002e904  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e909  mov     rcx, rsi; bstrString
0x18002e90c  mov     ebx, eax
0x18002e90e  call    cs:__imp_SysFreeString
0x18002e914  test    ebx, ebx
0x18002e916  js      short loc_18002E93D
0x18002e918  mov     edx, [rbp+4Fh+var_30]
0x18002e91b  mov     r9d, 1; unsigned int
0x18002e921  mov     eax, [rbp+4Fh+arg_20]
0x18002e924  inc     rdx
0x18002e927  mov     rcx, [rbp+4Fh+var_A8]; struct IAppHostSectionGroup *
0x18002e92b  mov     r8, r15; struct IIS_CONFIG_SECTION_DEFINITION *
0x18002e92e  mov     [rsp+0E0h+var_C0], eax; int
0x18002e932  lea     rdx, [r14+rdx*2]; unsigned __int16 *
0x18002e936  call    ?RecursivelyAddSectionDefinitions@CONFIG_SECTION_DEFINITION_HELPER@@CAJPEAUIAppHostSectionGroup@@PEBGQEAUIIS_CONFIG_SECTION_DEFINITION@@KH@Z; CONFIG_SECTION_DEFINITION_HELPER::RecursivelyAddSectionDefinitions(IAppHostSectionGroup *,ushort const *,IIS_CONFIG_SECTION_DEFINITION * const,ulong,int)
0x18002e93b  mov     ebx, eax
0x18002e93d  mov     rcx, [rbp+4Fh+var_B0]
0x18002e941  test    rcx, rcx
0x18002e944  jz      short loc_18002E95A
0x18002e946  mov     rax, [rcx]
0x18002e949  mov     rax, [rax+10h]
0x18002e94d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e952  mov     [rbp+4Fh+var_B0], 0
0x18002e95a  mov     rcx, [rbp+4Fh+var_A8]
0x18002e95e  test    rcx, rcx
0x18002e961  jz      short loc_18002E977
0x18002e963  mov     rax, [rcx]
0x18002e966  mov     rax, [rax+10h]
0x18002e96a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e96f  mov     [rbp+4Fh+var_A8], 0
0x18002e977  lea     rcx, [rbp+4Fh+var_60]; this
0x18002e97b  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18002e980  mov     eax, ebx
0x18002e982  mov     rcx, [rbp+4Fh+var_28]
0x18002e986  xor     rcx, rsp; StackCookie
0x18002e989  call    __security_check_cookie
0x18002e98e  mov     rbx, [rsp+0E0h+arg_18]
0x18002e996  add     rsp, 0C0h
0x18002e99d  pop     r15
0x18002e99f  pop     r14
0x18002e9a1  pop     rdi
0x18002e9a2  pop     rsi
0x18002e9a3  pop     rbp
0x18002e9a4  retn
```
