# Windows::FileSystem::ReFs::make_guid_str(void)

- ea: `0x14002caec`
- end: `0x14002cbab`
- name: `?make_guid_str@ReFs@FileSystem@Windows@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@XZ`
- size: `191`
- prototype: `__int64 __fastcall(LPOLESTR *lplpsz)`
- caller_count: `4`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140028c90`
- `0x1400290f0`
- `0x14002954c`
- `0x14003d2a4`

## callees

- `0x140004870`
- `0x140018f7c`
- `0x14002caec`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x14002cb1e`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x14002cb1e`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x14002cb6a`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x14002cb6a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
LPOLESTR *__fastcall Windows::FileSystem::ReFs::make_guid_str(LPOLESTR *lplpsz)
{
  HRESULT v2; // eax
  HRESULT v3; // eax
  GUID pguid; // [rsp+30h] [rbp-48h] BYREF
  LPOLESTR *v6; // [rsp+40h] [rbp-38h]
  IID rclsid; // [rsp+50h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v6 = lplpsz;
  pguid = 0;
  v2 = CoCreateGuid(&pguid);
  if ( v2 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x273,
      (unsigned int)"onecore\\base\\fs\\refsdedupsvc\\SvcLib\\inc\\SvcUtils.h",
      (const char *)(unsigned int)v2,
      0);
  rclsid = pguid;
  *lplpsz = 0;
  v3 = StringFromCLSID(&rclsid, lplpsz);
  if ( v3 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x27B,
      (unsigned int)"onecore\\base\\fs\\refsdedupsvc\\SvcLib\\inc\\SvcUtils.h",
      (const char *)(unsigned int)v3,
      1);
  return lplpsz;
}

```

## disassembly

```asm
0x14002caec  push    rbx
0x14002caee  sub     rsp, 70h
0x14002caf2  mov     rax, cs:__security_cookie
0x14002caf9  xor     rax, rsp
0x14002cafc  mov     [rsp+78h+var_18], rax
0x14002cb01  mov     rbx, rcx
0x14002cb04  mov     [rsp+78h+var_38], rcx
0x14002cb09  mov     [rsp+78h+var_58], 0; int
0x14002cb11  xorps   xmm0, xmm0
0x14002cb14  movups  xmmword ptr [rsp+78h+pguid.Data1], xmm0
0x14002cb19  lea     rcx, [rsp+78h+pguid]; pguid
0x14002cb1e  call    cs:__imp_CoCreateGuid
0x14002cb25  nop     dword ptr [rax+rax+00h]
0x14002cb2a  mov     rcx, [rsp+78h]; this
0x14002cb2f  test    eax, eax
0x14002cb31  jns     short loc_14002CB48
0x14002cb33  mov     r9d, eax; char *
0x14002cb36  lea     r8, aOnecoreBaseFsR_13; "onecore\\base\\fs\\refsdedupsvc\\SvcLib"...
0x14002cb3d  mov     edx, 273h; void *
0x14002cb42  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14002cb48  movaps  xmm0, xmmword ptr [rsp+78h+pguid.Data1]
0x14002cb4d  movdqa  xmmword ptr [rsp+78h+rclsid.Data1], xmm0
0x14002cb53  mov     [rsp+78h+var_58], 1; int
0x14002cb5b  mov     qword ptr [rbx], 0
0x14002cb62  mov     rdx, rbx; lplpsz
0x14002cb65  lea     rcx, [rsp+78h+rclsid]; rclsid
0x14002cb6a  call    cs:__imp_StringFromCLSID
0x14002cb71  nop     dword ptr [rax+rax+00h]
0x14002cb76  test    eax, eax
0x14002cb78  jns     short loc_14002CB94
0x14002cb7a  mov     rcx, [rsp+78h]; this
0x14002cb7f  mov     r9d, eax; char *
0x14002cb82  lea     r8, aOnecoreBaseFsR_13; "onecore\\base\\fs\\refsdedupsvc\\SvcLib"...
0x14002cb89  mov     edx, 27Bh; void *
0x14002cb8e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14002cb94  mov     rax, rbx
0x14002cb97  mov     rcx, [rsp+78h+var_18]
0x14002cb9c  xor     rcx, rsp; StackCookie
0x14002cb9f  call    __security_check_cookie
0x14002cba4  add     rsp, 70h
0x14002cba8  pop     rbx
0x14002cba9  retn
```
