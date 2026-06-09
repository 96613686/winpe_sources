# CFilterMapiFps::_InitAutoSummary(void)

- ea: `0x1800226d8`
- end: `0x18002279a`
- name: `?_InitAutoSummary@CFilterMapiFps@@AEAAXXZ`
- size: `194`
- prototype: `void __fastcall(CFilterMapiFps *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800204dc`
- `0x180020508`

## callees

- `0x18001e5d8`
- `0x18001e608`
- `0x180020768`
- `0x1800226d8`
- `0x18003f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022760`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022760`
- `PROPSYS!PSGetPropertyDescription` at `0x180022706`
- `PROPSYS!PSGetPropertyDescription` at `0x180022706`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall CFilterMapiFps::_InitAutoSummary(CFilterMapiFps *this)
{
  void *v2; // rcx
  CMapi2FullPropSpec *v3; // rcx
  CMapi2FullPropSpec *v4; // rcx
  const struct _GUID *PropGuid; // rax
  unsigned int v6; // edx
  const struct _tagpropertykey *v7; // r8
  unsigned int v8; // [rsp+30h] [rbp+8h] BYREF
  void *ppv; // [rsp+38h] [rbp+10h] BYREF

  if ( dword_18005927C )
  {
    ppv = 0;
    if ( PSGetPropertyDescription(&PKEY_Search_AutoSummary, &GUID_078f91bd_29a2_440f_924e_46a291524520, &ppv) >= 0 )
    {
      v8 = 0;
      if ( (*(int (__fastcall **)(void *, unsigned int *))(*(_QWORD *)ppv + 216LL))(ppv, &v8) >= 0 )
        LODWORD(dword_180059280) = v8 >> 1;
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
    }
  }
  v2 = (void *)*((_QWORD *)this + 14);
  dword_18005927C = 0;
  CoTaskMemFree(v2);
  v3 = (CMapi2FullPropSpec *)*((_QWORD *)this + 7);
  *((_QWORD *)this + 14) = 0;
  CMapi2FullPropSpec::GetPropId(v3);
  PropGuid = CMapi2FullPropSpec::GetPropGuid(v4);
  if ( (unsigned int)InlineIsEqualPKEY(PropGuid, v6, v7) )
    *((_DWORD *)this + 32) = 1;
}

```

## disassembly

```asm
0x1800226d8  push    rbx
0x1800226da  sub     rsp, 20h
0x1800226de  cmp     cs:dword_18005927C, 0
0x1800226e5  mov     rbx, rcx
0x1800226e8  jz      short loc_180022752
0x1800226ea  lea     r8, [rsp+28h+ppv]; ppv
0x1800226ef  mov     [rsp+28h+ppv], 0
0x1800226f8  lea     rdx, _GUID_078f91bd_29a2_440f_924e_46a291524520; riid
0x1800226ff  lea     rcx, PKEY_Search_AutoSummary; propkey
0x180022706  call    cs:__imp_PSGetPropertyDescription
0x18002270c  test    eax, eax
0x18002270e  js      short loc_180022752
0x180022710  mov     rcx, [rsp+28h+ppv]
0x180022715  lea     rdx, [rsp+28h+arg_0]
0x18002271a  mov     [rsp+28h+arg_0], 0
0x180022722  mov     rax, [rcx]
0x180022725  mov     rax, [rax+0D8h]
0x18002272c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022731  test    eax, eax
0x180022733  js      short loc_180022741
0x180022735  mov     eax, [rsp+28h+arg_0]
0x180022739  shr     eax, 1
0x18002273b  mov     cs:dword_180059280, eax
0x180022741  mov     rcx, [rsp+28h+ppv]
0x180022746  mov     rax, [rcx]
0x180022749  mov     rax, [rax+10h]
0x18002274d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022752  mov     rcx, [rbx+70h]; pv
0x180022756  mov     cs:dword_18005927C, 0
0x180022760  call    cs:__imp_CoTaskMemFree
0x180022766  mov     rcx, [rbx+38h]; this
0x18002276a  mov     qword ptr [rbx+70h], 0
0x180022772  call    ?GetPropId@CMapi2FullPropSpec@@QEBAKXZ; CMapi2FullPropSpec::GetPropId(void)
0x180022777  mov     edx, eax
0x180022779  call    ?GetPropGuid@CMapi2FullPropSpec@@QEBAAEBU_GUID@@XZ; CMapi2FullPropSpec::GetPropGuid(void)
0x18002277e  mov     rcx, rax; struct _GUID *
0x180022781  call    ?InlineIsEqualPKEY@@YAHAEBU_GUID@@KAEBU_tagpropertykey@@@Z; InlineIsEqualPKEY(_GUID const &,ulong,_tagpropertykey const &)
0x180022786  test    eax, eax
0x180022788  jz      short loc_180022794
0x18002278a  mov     dword ptr [rbx+80h], 1
0x180022794  add     rsp, 20h
0x180022798  pop     rbx
0x180022799  retn
```
