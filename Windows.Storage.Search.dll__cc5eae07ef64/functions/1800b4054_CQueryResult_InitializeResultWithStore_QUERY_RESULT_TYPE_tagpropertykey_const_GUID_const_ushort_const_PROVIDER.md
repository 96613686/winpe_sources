# CQueryResult::_InitializeResultWithStore(QUERY_RESULT_TYPE,_tagpropertykey const &,_GUID const &,ushort const *,PROVIDER_CAPABILITIES,STACK_ITEMID_MODE,IPropertyStoreCache *,QR_CMP_FLAGS)

- ea: `0x1800b4054`
- end: `0x1800b4283`
- name: `?_InitializeResultWithStore@CQueryResult@@AEAAJW4QUERY_RESULT_TYPE@@AEBU_tagpropertykey@@AEBU_GUID@@PEBGW4PROVIDER_CAPABILITIES@@W4STACK_ITEMID_MODE@@PEAUIPropertyStoreCache@@W4QR_CMP_FLAGS@@@Z`
- size: `559`
- prototype: ``
- caller_count: `4`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001cb30`
- `0x18001d280`
- `0x18004ef90`
- `0x18006381c`

## callees

- `0x180038020`
- `0x18003b260`
- `0x180045f00`
- `0x18004b66c`
- `0x18004e418`
- `0x180051868`
- `0x180051a1c`
- `0x18005737c`
- `0x180057838`
- `0x180063a68`
- `0x1800b4054`
- `0x1800ea010`

## import_xrefs

- `SHCORE!IUnknown_Set` at `0x1800b4248`
- `SHCORE!IUnknown_Set` at `0x1800b4248`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b4186`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b4190`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b4200`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b4186`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b4190`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b4200`

## pseudocode

```c
__int64 __fastcall CQueryResult::_InitializeResultWithStore(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        char a6,
        int a7,
        IUnknown *punk,
        int a9)
{
  struct IPropertyStore *v10; // rdi
  int String; // ebx
  __int64 v15; // rdx
  int savedregs; // [rsp+20h] [rbp+0h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+28h]
  LPVOID pv; // [rsp+50h] [rbp+30h] BYREF
  unsigned __int16 *v20; // [rsp+60h] [rbp+40h] BYREF

  v10 = (struct IPropertyStore *)punk;
  *(_DWORD *)(a1 + 208) = a9;
  *(_OWORD *)(a1 + 136) = *(_OWORD *)a3;
  *(_DWORD *)(a1 + 152) = *(_DWORD *)(a3 + 16);
  String = IPropertyStore_SetInt(v10, &PKEY_ResultType, a2);
  if ( String < 0 )
    goto LABEL_21;
  String = IPropertyStore_SetResultSourceId(v10, a3, a4, a5);
  if ( String < 0 )
    goto LABEL_21;
  if ( a2 != 1 )
  {
    a9 = 0;
    if ( !a7
      || ((int (__fastcall *)(struct IPropertyStore *, const PROPERTYKEY *, int *))v10->lpVtbl[1].QueryInterface)(
           v10,
           &PKEY_ItemId,
           &a9) < 0 )
    {
      pv = 0;
      String = IPropertyStore_GetString(v10, &PKEY_ItemNameDisplay, &pv);
      if ( String < 0 )
        goto LABEL_21;
      String = IPropertyStore_SetStringAlwaysTakeOwnership(v10, &PKEY_ItemId, (unsigned __int16 **)&pv);
      CoTaskMemFree(pv);
      if ( String < 0 )
        goto LABEL_21;
    }
    String = IPropertyStore_SetUInt32(v10, &PKEY_SFGAOFlags, 805306372);
    if ( String < 0 )
      goto LABEL_21;
    String = IPropertyStore_SetString(v10, &PKEY_ItemType, L"Stack");
    goto LABEL_19;
  }
  if ( (a6 & 0x40) == 0 )
  {
    String = IPropertyStore_SetBool(v10, PKEY_HasNoAdditionalProperties);
    if ( String < 0 )
      goto LABEL_21;
  }
  a9 = 0;
  IPropertyStore_GetBool(v10, v15, &a9);
  if ( !a9 )
  {
    pv = 0;
    v20 = 0;
    String = CQueryResult::_GetFixedNameAndPath((CQueryResult *)a1, v10, (unsigned __int16 **)&pv, &v20);
    if ( String < 0 )
      goto LABEL_21;
    if ( !pv
      || (String = IPropertyStore_SetStringAlwaysTakeOwnership(v10, &PKEY_ParsingPath, (unsigned __int16 **)&pv),
          String >= 0) )
    {
      if ( v20 )
        String = IPropertyStore_SetStringAlwaysTakeOwnership(v10, &PKEY_ItemNameDisplay, &v20);
    }
    CoTaskMemFree(pv);
    CoTaskMemFree(v20);
LABEL_19:
    if ( String >= 0 )
      goto LABEL_20;
LABEL_21:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA34,
      (unsigned int)"onecoreuap\\shell\\windows.storage.search\\resultsetfactory.cpp",
      (const char *)(unsigned int)String,
      savedregs);
    return (unsigned int)String;
  }
LABEL_20:
  IUnknown_Set((IUnknown **)(a1 + 104), (IUnknown *)v10);
  return 0;
}

```

## disassembly

```asm
0x1800b4054  mov     [rsp-28h+arg_8], rbx
0x1800b4059  mov     [rsp-28h+arg_18], rsi
0x1800b405e  push    rbp
0x1800b405f  push    rdi
0x1800b4060  push    r12
0x1800b4062  push    r14
0x1800b4064  push    r15; int
0x1800b4066  mov     rbp, rsp
0x1800b4069  sub     rsp, 20h
0x1800b406d  mov     eax, [rbp+arg_40]
0x1800b4070  mov     r15, r8
0x1800b4073  mov     rdi, [rbp+punk]
0x1800b4077  mov     r14d, edx
0x1800b407a  mov     [rcx+0D0h], eax
0x1800b4080  mov     rsi, rcx
0x1800b4083  movups  xmm0, xmmword ptr [r8]
0x1800b4087  mov     r12, r9
0x1800b408a  movups  xmmword ptr [rcx+88h], xmm0
0x1800b4091  mov     eax, [r8+10h]
0x1800b4095  mov     r8d, edx
0x1800b4098  mov     [rcx+98h], eax
0x1800b409e  lea     rdx, PKEY_ResultType
0x1800b40a5  mov     rcx, rdi
0x1800b40a8  call    IPropertyStore_SetInt
0x1800b40ad  mov     ebx, eax
0x1800b40af  test    eax, eax
0x1800b40b1  js      loc_1800B4252
0x1800b40b7  mov     r9, [rbp+arg_20]
0x1800b40bb  mov     r8, r12
0x1800b40be  mov     rdx, r15
0x1800b40c1  mov     rcx, rdi
0x1800b40c4  call    IPropertyStore_SetResultSourceId
0x1800b40c9  mov     ebx, eax
0x1800b40cb  test    eax, eax
0x1800b40cd  js      loc_1800B4252
0x1800b40d3  cmp     r14d, 1
0x1800b40d7  jnz     loc_1800B419B
0x1800b40dd  test    [rbp+arg_28], 40h
0x1800b40e1  jnz     short loc_1800B40FC
0x1800b40e3  lea     rdx, PKEY_HasNoAdditionalProperties
0x1800b40ea  mov     rcx, rdi
0x1800b40ed  call    IPropertyStore_SetBool
0x1800b40f2  mov     ebx, eax
0x1800b40f4  test    eax, eax
0x1800b40f6  js      loc_1800B4252
0x1800b40fc  lea     r8, [rbp+arg_40]
0x1800b4100  mov     [rbp+arg_40], 0
0x1800b4107  mov     rcx, rdi
0x1800b410a  call    IPropertyStore_GetBool
0x1800b410f  cmp     [rbp+arg_40], 0
0x1800b4113  jnz     loc_1800B4241
0x1800b4119  lea     r9, [rbp+arg_10]; unsigned __int16 **
0x1800b411d  mov     [rbp+pv], 0
0x1800b4125  lea     r8, [rbp+pv]; unsigned __int16 **
0x1800b4129  mov     [rbp+arg_10], 0
0x1800b4131  mov     rdx, rdi; struct IPropertyStore *
0x1800b4134  mov     rcx, rsi; this
0x1800b4137  call    ?_GetFixedNameAndPath@CQueryResult@@AEAAJPEAUIPropertyStore@@PEAPEAG1@Z; CQueryResult::_GetFixedNameAndPath(IPropertyStore *,ushort * *,ushort * *)
0x1800b413c  mov     ebx, eax
0x1800b413e  test    eax, eax
0x1800b4140  js      loc_1800B4252
0x1800b4146  cmp     [rbp+pv], 0
0x1800b414b  jz      short loc_1800B4166
0x1800b414d  lea     r8, [rbp+pv]; unsigned __int16 **
0x1800b4151  mov     rcx, rdi; struct IPropertyStore *
0x1800b4154  lea     rdx, PKEY_ParsingPath; struct _tagpropertykey *
0x1800b415b  call    ?IPropertyStore_SetStringAlwaysTakeOwnership@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@PEAPEAG@Z; IPropertyStore_SetStringAlwaysTakeOwnership(IPropertyStore *,_tagpropertykey const &,ushort * *)
0x1800b4160  mov     ebx, eax
0x1800b4162  test    eax, eax
0x1800b4164  js      short loc_1800B4182
0x1800b4166  cmp     [rbp+arg_10], 0
0x1800b416b  jz      short loc_1800B4182
0x1800b416d  lea     r8, [rbp+arg_10]; unsigned __int16 **
0x1800b4171  mov     rcx, rdi; struct IPropertyStore *
0x1800b4174  lea     rdx, PKEY_ItemNameDisplay; struct _tagpropertykey *
0x1800b417b  call    ?IPropertyStore_SetStringAlwaysTakeOwnership@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@PEAPEAG@Z; IPropertyStore_SetStringAlwaysTakeOwnership(IPropertyStore *,_tagpropertykey const &,ushort * *)
0x1800b4180  mov     ebx, eax
0x1800b4182  mov     rcx, [rbp+pv]; pv
0x1800b4186  call    cs:__imp_CoTaskMemFree
0x1800b418c  mov     rcx, [rbp+arg_10]; pv
0x1800b4190  call    cs:__imp_CoTaskMemFree
0x1800b4196  jmp     loc_1800B423D
0x1800b419b  cmp     [rbp+arg_30], 0
0x1800b419f  mov     [rbp+arg_40], 0
0x1800b41a6  jz      short loc_1800B41C6
0x1800b41a8  mov     rax, [rdi]
0x1800b41ab  lea     r8, [rbp+arg_40]
0x1800b41af  lea     rdx, PKEY_ItemId
0x1800b41b6  mov     rcx, rdi
0x1800b41b9  mov     rax, [rax+40h]
0x1800b41bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b41c2  test    eax, eax
0x1800b41c4  jns     short loc_1800B420A
0x1800b41c6  lea     r8, [rbp+pv]
0x1800b41ca  mov     [rbp+pv], 0
0x1800b41d2  lea     rdx, PKEY_ItemNameDisplay
0x1800b41d9  mov     rcx, rdi
0x1800b41dc  call    IPropertyStore_GetString
0x1800b41e1  mov     ebx, eax
0x1800b41e3  test    eax, eax
0x1800b41e5  js      short loc_1800B4252
0x1800b41e7  lea     r8, [rbp+pv]; unsigned __int16 **
0x1800b41eb  mov     rcx, rdi; struct IPropertyStore *
0x1800b41ee  lea     rdx, PKEY_ItemId; struct _tagpropertykey *
0x1800b41f5  call    ?IPropertyStore_SetStringAlwaysTakeOwnership@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@PEAPEAG@Z; IPropertyStore_SetStringAlwaysTakeOwnership(IPropertyStore *,_tagpropertykey const &,ushort * *)
0x1800b41fa  mov     rcx, [rbp+pv]; pv
0x1800b41fe  mov     ebx, eax
0x1800b4200  call    cs:__imp_CoTaskMemFree
0x1800b4206  test    ebx, ebx
0x1800b4208  js      short loc_1800B4252
0x1800b420a  mov     r8d, 30000004h
0x1800b4210  lea     rdx, PKEY_SFGAOFlags
0x1800b4217  mov     rcx, rdi
0x1800b421a  call    IPropertyStore_SetUInt32
0x1800b421f  mov     ebx, eax
0x1800b4221  test    eax, eax
0x1800b4223  js      short loc_1800B4252
0x1800b4225  lea     r8, aStack; "Stack"
0x1800b422c  mov     rcx, rdi
0x1800b422f  lea     rdx, PKEY_ItemType
0x1800b4236  call    IPropertyStore_SetString
0x1800b423b  mov     ebx, eax
0x1800b423d  test    ebx, ebx
0x1800b423f  js      short loc_1800B4252
0x1800b4241  lea     rcx, [rsi+68h]; ppunk
0x1800b4245  mov     rdx, rdi; punk
0x1800b4248  call    cs:__imp_IUnknown_Set
0x1800b424e  xor     ebx, ebx
0x1800b4250  jmp     short loc_1800B426A
0x1800b4252  mov     rcx, [rbp+28h]; this
0x1800b4256  lea     r8, aOnecoreuapShel_21; "onecoreuap\\shell\\windows.storage.sear"...
0x1800b425d  mov     r9d, ebx; char *
0x1800b4260  mov     edx, 0A34h; void *
0x1800b4265  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b426a  mov     rsi, [rsp+20h+arg_18]
0x1800b426f  mov     eax, ebx
0x1800b4271  mov     rbx, [rsp+20h+arg_8]
0x1800b4276  add     rsp, 20h
0x1800b427a  pop     r15
0x1800b427c  pop     r14
0x1800b427e  pop     r12
0x1800b4280  pop     rdi
0x1800b4281  pop     rbp
0x1800b4282  retn
```
