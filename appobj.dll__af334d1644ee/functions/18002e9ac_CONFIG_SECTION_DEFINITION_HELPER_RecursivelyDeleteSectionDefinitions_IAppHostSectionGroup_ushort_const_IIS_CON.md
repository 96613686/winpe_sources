# CONFIG_SECTION_DEFINITION_HELPER::RecursivelyDeleteSectionDefinitions(IAppHostSectionGroup *,ushort const *,IIS_CONFIG_SECTION_DEFINITION * const,ulong)

- ea: `0x18002e9ac`
- end: `0x18002eb5a`
- name: `?RecursivelyDeleteSectionDefinitions@CONFIG_SECTION_DEFINITION_HELPER@@CAJPEAUIAppHostSectionGroup@@PEBGQEAUIIS_CONFIG_SECTION_DEFINITION@@K@Z`
- size: `430`
- prototype: `__int64 __fastcall(struct IAppHostSectionGroup *, const unsigned __int16 *, struct IIS_CONFIG_SECTION_DEFINITION *const, unsigned int)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x1800194e4`
- `0x18002e9ac`

## callees

- `0x180001fb0`
- `0x18002e69c`
- `0x18002e720`
- `0x18002e9ac`
- `0x180034d00`
- `0x180036010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18002ea8e`
- `OLEAUT32!__imp_SysAllocString` at `0x18002ea8e`
- `OLEAUT32!__imp_VariantInit` at `0x18002ea7b`
- `OLEAUT32!__imp_VariantInit` at `0x18002ea7b`
- `OLEAUT32!__imp_VariantClear` at `0x18002ead3`
- `OLEAUT32!__imp_VariantClear` at `0x18002ead3`

## pseudocode

```c
__int64 __fastcall CONFIG_SECTION_DEFINITION_HELPER::RecursivelyDeleteSectionDefinitions(
        struct IAppHostSectionGroup *a1,
        const unsigned __int16 *a2,
        struct IIS_CONFIG_SECTION_DEFINITION *const a3)
{
  int NextSectionGroupName; // ebx
  int i; // edi
  HRESULT (__stdcall *get_Item)(IAppHostSectionGroup *, VARIANT, IAppHostSectionGroup **); // rax
  struct IAppHostSectionDefinitionCollection *v10; // [rsp+20h] [rbp-59h] BYREF
  struct IAppHostSectionGroup *v11; // [rsp+28h] [rbp-51h] BYREF
  VARIANTARG pvarg; // [rsp+30h] [rbp-49h] BYREF
  VARIANTARG v13; // [rsp+50h] [rbp-29h] BYREF
  _QWORD v14[4]; // [rsp+70h] [rbp-9h] BYREF
  OLECHAR *psz; // [rsp+90h] [rbp+17h]
  int v16; // [rsp+98h] [rbp+1Fh]
  __int16 v17; // [rsp+9Ch] [rbp+23h]
  int v18; // [rsp+A0h] [rbp+27h]

  v11 = 0;
  v14[0] = 0;
  v10 = 0;
  psz = (OLECHAR *)v14;
  v16 = 32;
  v17 = 256;
  v18 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  NextSectionGroupName = CONFIG_SECTION_DEFINITION_HELPER::GetNextSectionGroupName(a2, (struct STRU *)v14);
  if ( NextSectionGroupName >= 0 )
  {
    if ( v18 )
    {
      VariantInit(&pvarg);
      pvarg.vt = 8;
      pvarg.llVal = (LONGLONG)SysAllocString(psz);
      if ( pvarg.llVal )
      {
        get_Item = a1->lpVtbl->get_Item;
        v13 = pvarg;
        NextSectionGroupName = ((__int64 (__fastcall *)(struct IAppHostSectionGroup *, VARIANTARG *, struct IAppHostSectionGroup **))get_Item)(
                                 a1,
                                 &v13,
                                 &v11);
        VariantClear(&pvarg);
        if ( NextSectionGroupName >= 0 )
          NextSectionGroupName = CONFIG_SECTION_DEFINITION_HELPER::RecursivelyDeleteSectionDefinitions(
                                   v11,
                                   &a2[v18 + 1],
                                   a3,
                                   1u);
      }
      else
      {
        NextSectionGroupName = -2147024882;
      }
    }
    else
    {
      NextSectionGroupName = ((__int64 (__fastcall *)(struct IAppHostSectionGroup *, struct IAppHostSectionDefinitionCollection **))a1->lpVtbl->get_Sections)(
                               a1,
                               &v10);
      if ( NextSectionGroupName >= 0 )
      {
        for ( i = 0; !i; i = 1 )
        {
          NextSectionGroupName = CONFIG_SECTION_DEFINITION_HELPER::DeleteOneConfigSectionDefinition(
                                   v10,
                                   (const OLECHAR **)a3);
          if ( NextSectionGroupName < 0 )
            break;
        }
      }
    }
  }
  if ( v10 )
  {
    ((void (__fastcall *)(struct IAppHostSectionDefinitionCollection *))v10->lpVtbl->Release)(v10);
    v10 = 0;
  }
  if ( v11 )
  {
    ((void (__fastcall *)(struct IAppHostSectionGroup *))v11->lpVtbl->Release)(v11);
    v11 = 0;
  }
  BUFFER::~BUFFER((BUFFER *)v14);
  return (unsigned int)NextSectionGroupName;
}

```

## disassembly

```asm
0x18002e9ac  push    rbp
0x18002e9ae  push    rbx
0x18002e9af  push    rsi
0x18002e9b0  push    rdi
0x18002e9b1  push    r14
0x18002e9b3  lea     rbp, [rsp-37h]
0x18002e9b8  sub     rsp, 0B0h
0x18002e9bf  mov     rax, cs:__security_cookie
0x18002e9c6  xor     rax, rsp
0x18002e9c9  mov     [rbp+57h+var_28], rax
0x18002e9cd  xor     eax, eax
0x18002e9cf  mov     [rbp+57h+var_A8], 0
0x18002e9d7  mov     r14, rdx
0x18002e9da  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x18002e9de  mov     [rbp+57h+var_60], rax
0x18002e9e2  lea     rdx, [rbp+57h+var_60]; this
0x18002e9e6  lea     rax, [rbp+57h+var_60]
0x18002e9ea  mov     [rbp+57h+var_B0], 0
0x18002e9f2  mov     rdi, rcx
0x18002e9f5  mov     [rbp+57h+psz], rax
0x18002e9f9  xorps   xmm0, xmm0
0x18002e9fc  mov     [rbp+57h+var_38], 20h ; ' '
0x18002ea03  mov     rcx, r14; unsigned __int16 *
0x18002ea06  mov     [rbp+57h+var_34], 100h
0x18002ea0c  mov     rsi, r8
0x18002ea0f  mov     [rbp+57h+var_30], 0
0x18002ea16  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x18002ea1a  call    ?GetNextSectionGroupName@CONFIG_SECTION_DEFINITION_HELPER@@CAJPEBGPEAVSTRU@@@Z; CONFIG_SECTION_DEFINITION_HELPER::GetNextSectionGroupName(ushort const *,STRU *)
0x18002ea1f  mov     ebx, eax
0x18002ea21  test    eax, eax
0x18002ea23  js      loc_18002EAFB
0x18002ea29  cmp     [rbp+57h+var_30], 0
0x18002ea2d  jnz     short loc_18002EA77
0x18002ea2f  mov     rax, [rdi]
0x18002ea32  lea     rdx, [rbp+57h+var_B0]
0x18002ea36  mov     rcx, rdi
0x18002ea39  mov     rax, [rax+28h]
0x18002ea3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ea42  mov     ebx, eax
0x18002ea44  test    eax, eax
0x18002ea46  js      loc_18002EAFB
0x18002ea4c  xor     edi, edi
0x18002ea4e  cmp     edi, 1
0x18002ea51  jnb     loc_18002EAFB
0x18002ea57  mov     rcx, [rbp+57h+var_B0]; struct IAppHostSectionDefinitionCollection *
0x18002ea5b  mov     edx, edi
0x18002ea5d  shl     rdx, 5
0x18002ea61  add     rdx, rsi; struct IIS_CONFIG_SECTION_DEFINITION *
0x18002ea64  call    ?DeleteOneConfigSectionDefinition@CONFIG_SECTION_DEFINITION_HELPER@@CAJPEAUIAppHostSectionDefinitionCollection@@PEAUIIS_CONFIG_SECTION_DEFINITION@@@Z; CONFIG_SECTION_DEFINITION_HELPER::DeleteOneConfigSectionDefinition(IAppHostSectionDefinitionCollection *,IIS_CONFIG_SECTION_DEFINITION *)
0x18002ea69  mov     ebx, eax
0x18002ea6b  test    eax, eax
0x18002ea6d  js      loc_18002EAFB
0x18002ea73  inc     edi
0x18002ea75  jmp     short loc_18002EA4E
0x18002ea77  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18002ea7b  call    cs:__imp_VariantInit
0x18002ea81  mov     rcx, [rbp+57h+psz]; psz
0x18002ea85  mov     eax, 8
0x18002ea8a  mov     word ptr [rbp+57h+pvarg], ax
0x18002ea8e  call    cs:__imp_SysAllocString
0x18002ea94  mov     qword ptr [rbp+57h+pvarg+8], rax
0x18002ea98  test    rax, rax
0x18002ea9b  jnz     short loc_18002EAA4
0x18002ea9d  mov     ebx, 8007000Eh
0x18002eaa2  jmp     short loc_18002EAFB
0x18002eaa4  mov     rax, [rdi]
0x18002eaa7  lea     r8, [rbp+57h+var_A8]
0x18002eaab  movups  xmm0, xmmword ptr [rbp+57h+pvarg]
0x18002eaaf  lea     rdx, [rbp+57h+var_80]
0x18002eab3  mov     rcx, rdi
0x18002eab6  movsd   xmm1, qword ptr [rbp+57h+pvarg+10h]
0x18002eabb  mov     rax, [rax+20h]
0x18002eabf  movaps  [rbp+57h+var_80], xmm0
0x18002eac3  movsd   [rbp+57h+var_70], xmm1
0x18002eac8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002eacd  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18002ead1  mov     ebx, eax
0x18002ead3  call    cs:__imp_VariantClear
0x18002ead9  test    ebx, ebx
0x18002eadb  js      short loc_18002EAFB
0x18002eadd  mov     eax, [rbp+57h+var_30]
0x18002eae0  mov     r9d, 1; unsigned int
0x18002eae6  mov     rcx, [rbp+57h+var_A8]; struct IAppHostSectionGroup *
0x18002eaea  inc     rax
0x18002eaed  mov     r8, rsi; struct IIS_CONFIG_SECTION_DEFINITION *
0x18002eaf0  lea     rdx, [r14+rax*2]; unsigned __int16 *
0x18002eaf4  call    ?RecursivelyDeleteSectionDefinitions@CONFIG_SECTION_DEFINITION_HELPER@@CAJPEAUIAppHostSectionGroup@@PEBGQEAUIIS_CONFIG_SECTION_DEFINITION@@K@Z; CONFIG_SECTION_DEFINITION_HELPER::RecursivelyDeleteSectionDefinitions(IAppHostSectionGroup *,ushort const *,IIS_CONFIG_SECTION_DEFINITION * const,ulong)
0x18002eaf9  mov     ebx, eax
0x18002eafb  mov     rcx, [rbp+57h+var_B0]
0x18002eaff  test    rcx, rcx
0x18002eb02  jz      short loc_18002EB18
0x18002eb04  mov     rax, [rcx]
0x18002eb07  mov     rax, [rax+10h]
0x18002eb0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002eb10  mov     [rbp+57h+var_B0], 0
0x18002eb18  mov     rcx, [rbp+57h+var_A8]
0x18002eb1c  test    rcx, rcx
0x18002eb1f  jz      short loc_18002EB35
0x18002eb21  mov     rax, [rcx]
0x18002eb24  mov     rax, [rax+10h]
0x18002eb28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002eb2d  mov     [rbp+57h+var_A8], 0
0x18002eb35  lea     rcx, [rbp+57h+var_60]; this
0x18002eb39  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18002eb3e  mov     eax, ebx
0x18002eb40  mov     rcx, [rbp+57h+var_28]
0x18002eb44  xor     rcx, rsp; StackCookie
0x18002eb47  call    __security_check_cookie
0x18002eb4c  add     rsp, 0B0h
0x18002eb53  pop     r14
0x18002eb55  pop     rdi
0x18002eb56  pop     rsi
0x18002eb57  pop     rbx
0x18002eb58  pop     rbp
0x18002eb59  retn
```
