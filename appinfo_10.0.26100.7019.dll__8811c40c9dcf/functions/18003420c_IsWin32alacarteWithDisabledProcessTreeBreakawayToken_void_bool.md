# IsWin32alacarteWithDisabledProcessTreeBreakawayToken(void *,bool &)

- ea: `0x18003420c`
- end: `0x18003432b`
- name: `?IsWin32alacarteWithDisabledProcessTreeBreakawayToken@@YAJPEAXAEA_N@Z`
- size: `287`
- prototype: `__int64 __fastcall(void *, bool *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x180029474`

## callees

- `0x180007c78`
- `0x1800181cc`
- `0x18001b0c4`
- `0x18003420c`
- `0x180039410`

## import_xrefs

- `ntdll!RtlCompareUnicodeString` at `0x1800342f1`
- `ntdll!RtlCompareUnicodeString` at `0x1800342f1`
- `ntdll!RtlQueryPackageClaims` at `0x180034247`
- `ntdll!RtlQueryPackageClaims` at `0x180034247`

## string_xrefs

- `0x18003425c`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x1800342a5`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`

## pseudocode

```c
__int64 __fastcall IsWin32alacarteWithDisabledProcessTreeBreakawayToken(void *a1, bool *a2)
{
  int v4; // eax
  int token_information_nothrow; // eax
  unsigned int v7; // ebx
  _QWORD *v8; // rbx
  __int64 v9; // rdi
  __int64 v10; // rbp
  int v11; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  void *Block; // [rsp+68h] [rbp+10h] BYREF
  __int64 v14; // [rsp+70h] [rbp+18h] BYREF

  v14 = 0;
  *a2 = 0;
  v4 = RtlQueryPackageClaims(a1, 0, 0, 0, 0, 0, &v14, 0);
  if ( v4 < 0 )
    return wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)0x1F9,
             (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
             (const char *)(unsigned int)v4,
             v11);
  if ( (v14 & 0x10000) == 0 )
  {
    *a2 = 0;
    return 0;
  }
  Block = 0;
  token_information_nothrow = get_token_information_nothrow(&Block, a1);
  v7 = token_information_nothrow;
  if ( token_information_nothrow >= 0 )
  {
    v8 = Block;
    v9 = 0;
    if ( !*((_DWORD *)Block + 1) )
      goto LABEL_14;
    while ( 1 )
    {
      v10 = v8[1] + 40 * v9;
      if ( !RtlCompareUnicodeString(&String1, (PCUNICODE_STRING)v10, 1u) )
        break;
      v9 = (unsigned int)(v9 + 1);
      if ( (unsigned int)v9 >= *((_DWORD *)v8 + 1) )
        goto LABEL_14;
    }
    if ( (*(_BYTE *)(v10 + 20) & 1) == 0 )
LABEL_14:
      *a2 = 1;
    operator delete(v8);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x203,
    (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
    (const char *)(unsigned int)token_information_nothrow,
    v11);
  if ( Block )
    operator delete(Block);
  return v7;
}

```

## disassembly

```asm
0x18003420c  mov     r11, rsp
0x18003420f  mov     [r11+8], rbx
0x180034213  push    rbp
0x180034214  push    rsi
0x180034215  push    rdi
0x180034216  sub     rsp, 40h
0x18003421a  and     qword ptr [r11-20h], 0
0x18003421f  lea     rax, [r11+18h]
0x180034223  and     qword ptr [r11+18h], 0
0x180034228  mov     rsi, rdx
0x18003422b  mov     [r11-28h], rax
0x18003422f  xor     r9d, r9d
0x180034232  and     qword ptr [r11-30h], 0
0x180034237  xor     r8d, r8d
0x18003423a  and     qword ptr [r11-38h], 0
0x18003423f  mov     rbx, rcx
0x180034242  mov     byte ptr [rdx], 0
0x180034245  xor     edx, edx
0x180034247  call    cs:__imp_RtlQueryPackageClaims
0x18003424e  nop     dword ptr [rax+rax+00h]
0x180034253  test    eax, eax
0x180034255  jns     short loc_180034275
0x180034257  mov     rcx, [rsp+58h]; this
0x18003425c  lea     r8, aOnecoreuapDsSe_0; "onecoreuap\\ds\\security\\services\\lua"...
0x180034263  mov     r9d, eax; char *
0x180034266  mov     edx, 1F9h; void *
0x18003426b  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180034270  jmp     loc_18003431D
0x180034275  test    dword ptr [rsp+58h+arg_10], 10000h
0x18003427d  jnz     short loc_180034287
0x18003427f  mov     byte ptr [rsi], 0
0x180034282  jmp     loc_18003431B
0x180034287  and     [rsp+58h+Block], 0
0x18003428d  lea     rcx, [rsp+58h+Block]
0x180034292  mov     rdx, rbx
0x180034295  call    ?get_token_information_nothrow@@YAJAEAV?$unique_ptr@U_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z; get_token_information_nothrow(wistd::unique_ptr<_TOKEN_SECURITY_ATTRIBUTES_INFORMATION,wil::details::token_info_deleter> &,void *)
0x18003429a  mov     ebx, eax
0x18003429c  test    eax, eax
0x18003429e  jns     short loc_1800342CC
0x1800342a0  mov     rcx, [rsp+58h]; this
0x1800342a5  lea     r8, aOnecoreuapDsSe_0; "onecoreuap\\ds\\security\\services\\lua"...
0x1800342ac  mov     r9d, eax; char *
0x1800342af  mov     edx, 203h; void *
0x1800342b4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800342b9  mov     rcx, [rsp+58h+Block]; Block
0x1800342be  test    rcx, rcx
0x1800342c1  jz      short loc_1800342C8
0x1800342c3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800342c8  mov     eax, ebx
0x1800342ca  jmp     short loc_18003431D
0x1800342cc  mov     rbx, [rsp+58h+Block]
0x1800342d1  xor     edi, edi
0x1800342d3  cmp     [rbx+4], edi
0x1800342d6  jbe     short loc_180034310
0x1800342d8  mov     rax, [rbx+8]
0x1800342dc  lea     rcx, [rdi+rdi*4]
0x1800342e0  mov     r8b, 1; CaseInsensitive
0x1800342e3  lea     rbp, [rax+rcx*8]
0x1800342e7  mov     rdx, rbp; String2
0x1800342ea  lea     rcx, String1; String1
0x1800342f1  call    cs:__imp_RtlCompareUnicodeString
0x1800342f8  nop     dword ptr [rax+rax+00h]
0x1800342fd  test    eax, eax
0x1800342ff  jz      short loc_18003430A
0x180034301  inc     edi
0x180034303  cmp     edi, [rbx+4]
0x180034306  jb      short loc_1800342D8
0x180034308  jmp     short loc_180034310
0x18003430a  test    byte ptr [rbp+14h], 1
0x18003430e  jnz     short loc_180034313
0x180034310  mov     byte ptr [rsi], 1
0x180034313  mov     rcx, rbx; Block
0x180034316  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003431b  xor     eax, eax
0x18003431d  mov     rbx, [rsp+58h+arg_0]
0x180034322  add     rsp, 40h
0x180034326  pop     rdi
0x180034327  pop     rsi
0x180034328  pop     rbp
0x180034329  retn
```
