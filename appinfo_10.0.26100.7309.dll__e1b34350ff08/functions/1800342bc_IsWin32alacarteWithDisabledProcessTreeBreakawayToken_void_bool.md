# IsWin32alacarteWithDisabledProcessTreeBreakawayToken(void *,bool &)

- ea: `0x1800342bc`
- end: `0x1800343db`
- name: `?IsWin32alacarteWithDisabledProcessTreeBreakawayToken@@YAJPEAXAEA_N@Z`
- size: `287`
- prototype: `__int64 __fastcall(void *, bool *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x180027d78`

## callees

- `0x180007c78`
- `0x18001847c`
- `0x18001b494`
- `0x1800342bc`
- `0x180039b60`

## import_xrefs

- `ntdll!RtlCompareUnicodeString` at `0x1800343a1`
- `ntdll!RtlCompareUnicodeString` at `0x1800343a1`
- `ntdll!RtlQueryPackageClaims` at `0x1800342f7`
- `ntdll!RtlQueryPackageClaims` at `0x1800342f7`

## string_xrefs

- `0x18003430c`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180034355`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`

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
             (void *)0x1F7,
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
    (void *)0x201,
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
0x1800342bc  mov     r11, rsp
0x1800342bf  mov     [r11+8], rbx
0x1800342c3  push    rbp
0x1800342c4  push    rsi
0x1800342c5  push    rdi
0x1800342c6  sub     rsp, 40h
0x1800342ca  and     qword ptr [r11-20h], 0
0x1800342cf  lea     rax, [r11+18h]
0x1800342d3  and     qword ptr [r11+18h], 0
0x1800342d8  mov     rsi, rdx
0x1800342db  mov     [r11-28h], rax
0x1800342df  xor     r9d, r9d
0x1800342e2  and     qword ptr [r11-30h], 0
0x1800342e7  xor     r8d, r8d
0x1800342ea  and     qword ptr [r11-38h], 0
0x1800342ef  mov     rbx, rcx
0x1800342f2  mov     byte ptr [rdx], 0
0x1800342f5  xor     edx, edx
0x1800342f7  call    cs:__imp_RtlQueryPackageClaims
0x1800342fe  nop     dword ptr [rax+rax+00h]
0x180034303  test    eax, eax
0x180034305  jns     short loc_180034325
0x180034307  mov     rcx, [rsp+58h]; this
0x18003430c  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x180034313  mov     r9d, eax; char *
0x180034316  mov     edx, 1F7h; void *
0x18003431b  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180034320  jmp     loc_1800343CD
0x180034325  test    dword ptr [rsp+58h+arg_10], 10000h
0x18003432d  jnz     short loc_180034337
0x18003432f  mov     byte ptr [rsi], 0
0x180034332  jmp     loc_1800343CB
0x180034337  and     [rsp+58h+Block], 0
0x18003433d  lea     rcx, [rsp+58h+Block]
0x180034342  mov     rdx, rbx
0x180034345  call    ?get_token_information_nothrow@@YAJAEAV?$unique_ptr@U_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z; get_token_information_nothrow(wistd::unique_ptr<_TOKEN_SECURITY_ATTRIBUTES_INFORMATION,wil::details::token_info_deleter> &,void *)
0x18003434a  mov     ebx, eax
0x18003434c  test    eax, eax
0x18003434e  jns     short loc_18003437C
0x180034350  mov     rcx, [rsp+58h]; this
0x180034355  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x18003435c  mov     r9d, eax; char *
0x18003435f  mov     edx, 201h; void *
0x180034364  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180034369  mov     rcx, [rsp+58h+Block]; Block
0x18003436e  test    rcx, rcx
0x180034371  jz      short loc_180034378
0x180034373  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180034378  mov     eax, ebx
0x18003437a  jmp     short loc_1800343CD
0x18003437c  mov     rbx, [rsp+58h+Block]
0x180034381  xor     edi, edi
0x180034383  cmp     [rbx+4], edi
0x180034386  jbe     short loc_1800343C0
0x180034388  mov     rax, [rbx+8]
0x18003438c  lea     rcx, [rdi+rdi*4]
0x180034390  mov     r8b, 1; CaseInsensitive
0x180034393  lea     rbp, [rax+rcx*8]
0x180034397  mov     rdx, rbp; String2
0x18003439a  lea     rcx, String1; String1
0x1800343a1  call    cs:__imp_RtlCompareUnicodeString
0x1800343a8  nop     dword ptr [rax+rax+00h]
0x1800343ad  test    eax, eax
0x1800343af  jz      short loc_1800343BA
0x1800343b1  inc     edi
0x1800343b3  cmp     edi, [rbx+4]
0x1800343b6  jb      short loc_180034388
0x1800343b8  jmp     short loc_1800343C0
0x1800343ba  test    byte ptr [rbp+14h], 1
0x1800343be  jnz     short loc_1800343C3
0x1800343c0  mov     byte ptr [rsi], 1
0x1800343c3  mov     rcx, rbx; Block
0x1800343c6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800343cb  xor     eax, eax
0x1800343cd  mov     rbx, [rsp+58h+arg_0]
0x1800343d2  add     rsp, 40h
0x1800343d6  pop     rdi
0x1800343d7  pop     rsi
0x1800343d8  pop     rbp
0x1800343d9  retn
```
