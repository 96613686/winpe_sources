# IsWin32alacarteWithDisabledProcessTreeBreakawayToken(void *,bool &)

- ea: `0x18003457c`
- end: `0x18003469b`
- name: `?IsWin32alacarteWithDisabledProcessTreeBreakawayToken@@YAJPEAXAEA_N@Z`
- size: `287`
- prototype: `__int64 __fastcall(void *, bool *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x180028604`

## callees

- `0x180007c78`
- `0x18001847c`
- `0x18001b494`
- `0x18003457c`
- `0x180039ee0`

## import_xrefs

- `ntdll!RtlCompareUnicodeString` at `0x180034661`
- `ntdll!RtlCompareUnicodeString` at `0x180034661`
- `ntdll!RtlQueryPackageClaims` at `0x1800345b7`
- `ntdll!RtlQueryPackageClaims` at `0x1800345b7`

## string_xrefs

- `0x1800345cc`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180034615`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`

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
             (void *)0x1F8,
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
    (void *)0x202,
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
0x18003457c  mov     r11, rsp
0x18003457f  mov     [r11+8], rbx
0x180034583  push    rbp
0x180034584  push    rsi
0x180034585  push    rdi
0x180034586  sub     rsp, 40h
0x18003458a  and     qword ptr [r11-20h], 0
0x18003458f  lea     rax, [r11+18h]
0x180034593  and     qword ptr [r11+18h], 0
0x180034598  mov     rsi, rdx
0x18003459b  mov     [r11-28h], rax
0x18003459f  xor     r9d, r9d
0x1800345a2  and     qword ptr [r11-30h], 0
0x1800345a7  xor     r8d, r8d
0x1800345aa  and     qword ptr [r11-38h], 0
0x1800345af  mov     rbx, rcx
0x1800345b2  mov     byte ptr [rdx], 0
0x1800345b5  xor     edx, edx
0x1800345b7  call    cs:__imp_RtlQueryPackageClaims
0x1800345be  nop     dword ptr [rax+rax+00h]
0x1800345c3  test    eax, eax
0x1800345c5  jns     short loc_1800345E5
0x1800345c7  mov     rcx, [rsp+58h]; this
0x1800345cc  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x1800345d3  mov     r9d, eax; char *
0x1800345d6  mov     edx, 1F8h; void *
0x1800345db  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800345e0  jmp     loc_18003468D
0x1800345e5  test    dword ptr [rsp+58h+arg_10], 10000h
0x1800345ed  jnz     short loc_1800345F7
0x1800345ef  mov     byte ptr [rsi], 0
0x1800345f2  jmp     loc_18003468B
0x1800345f7  and     [rsp+58h+Block], 0
0x1800345fd  lea     rcx, [rsp+58h+Block]
0x180034602  mov     rdx, rbx
0x180034605  call    ?get_token_information_nothrow@@YAJAEAV?$unique_ptr@U_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z; get_token_information_nothrow(wistd::unique_ptr<_TOKEN_SECURITY_ATTRIBUTES_INFORMATION,wil::details::token_info_deleter> &,void *)
0x18003460a  mov     ebx, eax
0x18003460c  test    eax, eax
0x18003460e  jns     short loc_18003463C
0x180034610  mov     rcx, [rsp+58h]; this
0x180034615  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x18003461c  mov     r9d, eax; char *
0x18003461f  mov     edx, 202h; void *
0x180034624  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180034629  mov     rcx, [rsp+58h+Block]; Block
0x18003462e  test    rcx, rcx
0x180034631  jz      short loc_180034638
0x180034633  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180034638  mov     eax, ebx
0x18003463a  jmp     short loc_18003468D
0x18003463c  mov     rbx, [rsp+58h+Block]
0x180034641  xor     edi, edi
0x180034643  cmp     [rbx+4], edi
0x180034646  jbe     short loc_180034680
0x180034648  mov     rax, [rbx+8]
0x18003464c  lea     rcx, [rdi+rdi*4]
0x180034650  mov     r8b, 1; CaseInsensitive
0x180034653  lea     rbp, [rax+rcx*8]
0x180034657  mov     rdx, rbp; String2
0x18003465a  lea     rcx, String1; String1
0x180034661  call    cs:__imp_RtlCompareUnicodeString
0x180034668  nop     dword ptr [rax+rax+00h]
0x18003466d  test    eax, eax
0x18003466f  jz      short loc_18003467A
0x180034671  inc     edi
0x180034673  cmp     edi, [rbx+4]
0x180034676  jb      short loc_180034648
0x180034678  jmp     short loc_180034680
0x18003467a  test    byte ptr [rbp+14h], 1
0x18003467e  jnz     short loc_180034683
0x180034680  mov     byte ptr [rsi], 1
0x180034683  mov     rcx, rbx; Block
0x180034686  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003468b  xor     eax, eax
0x18003468d  mov     rbx, [rsp+58h+arg_0]
0x180034692  add     rsp, 40h
0x180034696  pop     rdi
0x180034697  pop     rsi
0x180034698  pop     rbp
0x180034699  retn
```
