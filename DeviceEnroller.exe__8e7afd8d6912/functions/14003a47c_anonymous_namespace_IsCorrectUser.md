# _anonymous_namespace_::IsCorrectUser

- ea: `0x14003a47c`
- end: `0x14003a4ec`
- name: `_anonymous_namespace_::IsCorrectUser`
- size: `112`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140039730`

## callees

- `0x14000a6e4`
- `0x14003a47c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14003a4b3`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14003a4b3`
- `DMCmnUtils!DmGetActiveUserSid` at `0x14003a49c`
- `DMCmnUtils!DmGetActiveUserSid` at `0x14003a49c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14003a4c9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14003a4c9`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall anonymous_namespace_::IsCorrectUser(__int64 a1)
{
  int ActiveUserSid; // eax
  bool v4; // bl
  int v5; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  HLOCAL hMem; // [rsp+30h] [rbp+8h] BYREF

  if ( !a1 )
    return 1;
  hMem = 0;
  ActiveUserSid = DmGetActiveUserSid((unsigned __int16 **)&hMem);
  if ( ActiveUserSid < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x2C,
      (int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\dynamicmanagement.cpp",
      (const char *)(unsigned int)ActiveUserSid,
      v5);
  v4 = (unsigned int)_o__wcsicmp(hMem, a1) != 0;
  if ( hMem )
    LocalFree(hMem);
  return v4;
}

```

## disassembly

```asm
0x14003a47c  push    rbx; int
0x14003a47e  sub     rsp, 20h
0x14003a482  mov     rbx, rcx
0x14003a485  test    rcx, rcx
0x14003a488  jnz     short loc_14003A48E
0x14003a48a  mov     al, 1
0x14003a48c  jmp     short loc_14003A4D1
0x14003a48e  mov     [rsp+28h+hMem], 0
0x14003a497  lea     rcx, [rsp+28h+hMem]
0x14003a49c  call    cs:__imp_?DmGetActiveUserSid@@YAJPEAPEAG@Z; DmGetActiveUserSid(ushort * *)
0x14003a4a2  mov     rcx, [rsp+28h]; this
0x14003a4a7  test    eax, eax
0x14003a4a9  js      short loc_14003A4D7
0x14003a4ab  mov     rdx, rbx
0x14003a4ae  mov     rcx, [rsp+28h+hMem]
0x14003a4b3  call    cs:__imp__o__wcsicmp
0x14003a4b9  nop
0x14003a4ba  test    eax, eax
0x14003a4bc  setnz   bl
0x14003a4bf  mov     rcx, [rsp+28h+hMem]; hMem
0x14003a4c4  test    rcx, rcx
0x14003a4c7  jz      short loc_14003A4CF
0x14003a4c9  call    cs:__imp_LocalFree
0x14003a4cf  mov     al, bl
0x14003a4d1  add     rsp, 20h
0x14003a4d5  pop     rbx
0x14003a4d6  retn
0x14003a4d7  mov     r9d, eax; char *
0x14003a4da  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x14003a4e1  mov     edx, 2Ch ; ','; void *
0x14003a4e6  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
