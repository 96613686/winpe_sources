# IsWin32alacarteWithDisabledProcessTreeBreakawayToken(void *,bool &)

- ea: `0x1800375fc`
- end: `0x180037722`
- name: `?IsWin32alacarteWithDisabledProcessTreeBreakawayToken@@YAJPEAXAEA_N@Z`
- size: `294`
- prototype: `__int64 __fastcall(void *, bool *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x18002b27c`

## callees

- `0x18000720c`
- `0x180018190`
- `0x18001e7bc`
- `0x1800375fc`
- `0x18003c380`

## import_xrefs

- `ntdll!RtlCompareUnicodeString` at `0x1800376ea`
- `ntdll!RtlCompareUnicodeString` at `0x1800376ea`
- `ntdll!RtlQueryPackageClaims` at `0x180037643`
- `ntdll!RtlQueryPackageClaims` at `0x180037643`

## string_xrefs

- `0x180037652`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18003769e`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`

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

  *a2 = 0;
  v14 = 0;
  v4 = RtlQueryPackageClaims(a1, 0, 0, 0, 0, 0, &v14, 0);
  if ( v4 < 0 )
    return wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)0x303,
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
    if ( v8 )
      operator delete(v8);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x30D,
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
0x1800375fc  mov     r11, rsp
0x1800375ff  mov     [r11+8], rbx
0x180037603  push    rbp
0x180037604  push    rsi
0x180037605  push    rdi
0x180037606  sub     rsp, 40h
0x18003760a  mov     qword ptr [r11-20h], 0
0x180037612  lea     rax, [r11+18h]
0x180037616  mov     [r11-28h], rax
0x18003761a  mov     rsi, rdx
0x18003761d  mov     byte ptr [rdx], 0
0x180037620  xor     r9d, r9d
0x180037623  mov     qword ptr [r11-30h], 0
0x18003762b  xor     r8d, r8d
0x18003762e  xor     edx, edx
0x180037630  mov     qword ptr [r11-38h], 0
0x180037638  mov     rbx, rcx
0x18003763b  mov     qword ptr [r11+18h], 0
0x180037643  call    cs:__imp_RtlQueryPackageClaims
0x180037649  test    eax, eax
0x18003764b  jns     short loc_18003766B
0x18003764d  mov     rcx, [rsp+58h]; this
0x180037652  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x180037659  mov     r9d, eax; char *
0x18003765c  mov     edx, 303h; void *
0x180037661  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180037666  jmp     loc_180037715
0x18003766b  test    dword ptr [rsp+58h+arg_10], 10000h
0x180037673  jnz     short loc_18003767D
0x180037675  mov     byte ptr [rsi], 0
0x180037678  jmp     loc_180037713
0x18003767d  mov     rdx, rbx
0x180037680  mov     [rsp+58h+Block], 0
0x180037689  lea     rcx, [rsp+58h+Block]
0x18003768e  call    ?get_token_information_nothrow@@YAJAEAV?$unique_ptr@U_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z; get_token_information_nothrow(wistd::unique_ptr<_TOKEN_SECURITY_ATTRIBUTES_INFORMATION,wil::details::token_info_deleter> &,void *)
0x180037693  mov     ebx, eax
0x180037695  test    eax, eax
0x180037697  jns     short loc_1800376C5
0x180037699  mov     rcx, [rsp+58h]; this
0x18003769e  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x1800376a5  mov     r9d, eax; char *
0x1800376a8  mov     edx, 30Dh; void *
0x1800376ad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800376b2  mov     rcx, [rsp+58h+Block]; Block
0x1800376b7  test    rcx, rcx
0x1800376ba  jz      short loc_1800376C1
0x1800376bc  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800376c1  mov     eax, ebx
0x1800376c3  jmp     short loc_180037715
0x1800376c5  mov     rbx, [rsp+58h+Block]
0x1800376ca  xor     edi, edi
0x1800376cc  cmp     [rbx+4], edi
0x1800376cf  jbe     short loc_180037703
0x1800376d1  mov     rax, [rbx+8]
0x1800376d5  lea     rcx, [rdi+rdi*4]
0x1800376d9  mov     r8b, 1; CaseInsensitive
0x1800376dc  lea     rbp, [rax+rcx*8]
0x1800376e0  mov     rdx, rbp; String2
0x1800376e3  lea     rcx, String1; String1
0x1800376ea  call    cs:__imp_RtlCompareUnicodeString
0x1800376f0  test    eax, eax
0x1800376f2  jz      short loc_1800376FD
0x1800376f4  inc     edi
0x1800376f6  cmp     edi, [rbx+4]
0x1800376f9  jb      short loc_1800376D1
0x1800376fb  jmp     short loc_180037703
0x1800376fd  test    byte ptr [rbp+14h], 1
0x180037701  jnz     short loc_180037706
0x180037703  mov     byte ptr [rsi], 1
0x180037706  test    rbx, rbx
0x180037709  jz      short loc_180037713
0x18003770b  mov     rcx, rbx; Block
0x18003770e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180037713  xor     eax, eax
0x180037715  mov     rbx, [rsp+58h+arg_0]
0x18003771a  add     rsp, 40h
0x18003771e  pop     rdi
0x18003771f  pop     rsi
0x180037720  pop     rbp
0x180037721  retn
```
