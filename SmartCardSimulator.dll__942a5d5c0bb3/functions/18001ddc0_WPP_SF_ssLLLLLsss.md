# WPP_SF_ssLLLLLsss

- ea: `0x18001ddc0`
- end: `0x18001df5e`
- name: `WPP_SF_ssLLLLLsss`
- size: `414`
- prototype: `__int64 __usercall@<rax>(TRACEHANDLE LoggerHandle@<rcx>, int, char, char, char, char, char, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800125d8`

## callees

- `0x18001ddc0`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18001df4c`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18001df4c`

## string_xrefs

- `0x18001df2d`: `Channel::PreCommand::Select`

## pseudocode

```c
ULONG __fastcall WPP_SF_ssLLLLLsss(
        TRACEHANDLE LoggerHandle,
        __int64 a2,
        __int64 a3,
        const char *a4,
        int a5,
        char a6,
        char a7,
        char a8,
        char a9,
        char a10,
        const char *a11,
        const char *a12,
        const char *a13)
{
  const char *v13; // r8
  __int64 v14; // rax
  __int64 v17; // r10
  __int64 v18; // rdx
  __int64 v19; // rdi
  const char *v20; // r9
  __int64 v21; // rcx
  __int64 v22; // rbx
  const char *v23; // rcx
  __int64 v24; // rdx
  __int64 v25; // rdx
  bool v26; // zf

  v13 = a13;
  v14 = -1;
  v17 = 5;
  if ( a13 )
  {
    v18 = -1;
    do
      ++v18;
    while ( a13[v18] );
    v19 = v18 + 1;
  }
  else
  {
    v19 = 5;
  }
  v20 = a12;
  if ( !a13 )
    v13 = "NULL";
  if ( a12 )
  {
    v21 = -1;
    do
      ++v21;
    while ( a12[v21] );
    v22 = v21 + 1;
  }
  else
  {
    v22 = 5;
  }
  v23 = a11;
  if ( !a12 )
    v20 = "NULL";
  if ( a11 )
  {
    v24 = -1;
    do
      ++v24;
    while ( a11[v24] );
    v25 = v24 + 1;
  }
  else
  {
    v25 = 5;
  }
  if ( !a11 )
    v23 = "NULL";
  v26 = a4 == 0;
  if ( a4 )
  {
    do
      ++v14;
    while ( a4[v14] );
    v17 = v14 + 1;
    v26 = a4 == 0;
  }
  if ( v26 )
    a4 = "NULL";
  return TraceMessage(
           LoggerHandle,
           0x2Bu,
           &WPP_af6c915c0e3c3e5aff280afce4c18d8e_Traceguids,
           0x1Au,
           a4,
           v17,
           "Channel::PreCommand::Select",
           28,
           &a6,
           4,
           &a7,
           4,
           &a8,
           4,
           &a9,
           4,
           &a10,
           4,
           v23,
           v25,
           v20,
           v22,
           v13,
           v19,
           0);
}

```

## disassembly

```asm
0x18001ddc0  push    rbx
0x18001ddc2  push    rbp
0x18001ddc3  push    rsi
0x18001ddc4  push    rdi
0x18001ddc5  sub     rsp, 0D8h
0x18001ddcc  mov     r8, [rsp+0F8h+arg_60]
0x18001ddd4  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001ddd8  mov     r11, r9
0x18001dddb  mov     rsi, rcx
0x18001ddde  mov     r10d, 5
0x18001dde4  test    r8, r8
0x18001dde7  jz      short loc_18001DDFC
0x18001dde9  mov     rdx, rax
0x18001ddec  inc     rdx
0x18001ddef  cmp     byte ptr [r8+rdx], 0
0x18001ddf4  jnz     short loc_18001DDEC
0x18001ddf6  lea     rdi, [rdx+1]
0x18001ddfa  jmp     short loc_18001DDFF
0x18001ddfc  mov     rdi, r10
0x18001ddff  mov     r9, [rsp+0F8h+arg_58]
0x18001de07  lea     rbp, aNull; "NULL"
0x18001de0e  test    r8, r8
0x18001de11  cmovz   r8, rbp
0x18001de15  test    r9, r9
0x18001de18  jz      short loc_18001DE2D
0x18001de1a  mov     rcx, rax
0x18001de1d  inc     rcx
0x18001de20  cmp     byte ptr [r9+rcx], 0
0x18001de25  jnz     short loc_18001DE1D
0x18001de27  lea     rbx, [rcx+1]
0x18001de2b  jmp     short loc_18001DE30
0x18001de2d  mov     rbx, r10
0x18001de30  mov     rcx, [rsp+0F8h+arg_50]
0x18001de38  test    r9, r9
0x18001de3b  cmovz   r9, rbp
0x18001de3f  test    rcx, rcx
0x18001de42  jz      short loc_18001DE55
0x18001de44  mov     rdx, rax
0x18001de47  inc     rdx
0x18001de4a  cmp     byte ptr [rcx+rdx], 0
0x18001de4e  jnz     short loc_18001DE47
0x18001de50  inc     rdx
0x18001de53  jmp     short loc_18001DE58
0x18001de55  mov     rdx, r10
0x18001de58  test    rcx, rcx
0x18001de5b  cmovz   rcx, rbp
0x18001de5f  test    r11, r11
0x18001de62  jz      short loc_18001DE75
0x18001de64  inc     rax
0x18001de67  cmp     byte ptr [r11+rax], 0
0x18001de6c  jnz     short loc_18001DE64
0x18001de6e  lea     r10, [rax+1]
0x18001de72  test    r11, r11
0x18001de75  mov     [rsp+0F8h+var_38], 0
0x18001de81  lea     rax, [rsp+0F8h+arg_48]
0x18001de89  mov     [rsp+0F8h+var_40], rdi
0x18001de91  cmovz   r11, rbp
0x18001de95  mov     [rsp+0F8h+var_48], r8
0x18001de9d  mov     ebp, 1Ah
0x18001dea2  mov     [rsp+0F8h+var_50], rbx
0x18001deaa  lea     r8, WPP_af6c915c0e3c3e5aff280afce4c18d8e_Traceguids; MessageGuid
0x18001deb1  mov     [rsp+0F8h+var_58], r9
0x18001deb9  mov     r9d, ebp; MessageNumber
0x18001debc  mov     [rsp+0F8h+var_60], rdx
0x18001dec4  mov     [rsp+0F8h+var_68], rcx
0x18001decc  lea     edx, [rbp+11h]; MessageFlags
0x18001decf  lea     ecx, [rbp-16h]
0x18001ded2  mov     [rsp+0F8h+var_70], rcx
0x18001deda  mov     [rsp+0F8h+var_78], rax
0x18001dee2  lea     rax, [rsp+0F8h+arg_40]
0x18001deea  mov     [rsp+0F8h+var_80], rcx
0x18001deef  mov     [rsp+0F8h+var_88], rax
0x18001def4  lea     rax, [rsp+0F8h+arg_38]
0x18001defc  mov     [rsp+0F8h+var_90], rcx
0x18001df01  mov     [rsp+0F8h+var_98], rax
0x18001df06  lea     rax, [rsp+0F8h+arg_30]
0x18001df0e  mov     [rsp+0F8h+var_A0], rcx
0x18001df13  mov     [rsp+0F8h+var_A8], rax
0x18001df18  lea     rax, [rsp+0F8h+arg_28]
0x18001df20  mov     [rsp+0F8h+var_B0], rcx
0x18001df25  mov     rcx, rsi; LoggerHandle
0x18001df28  mov     [rsp+0F8h+var_B8], rax
0x18001df2d  lea     rax, aChannelPrecomm; "Channel::PreCommand::Select"
0x18001df34  mov     [rsp+0F8h+var_C0], 1Ch
0x18001df3d  mov     [rsp+0F8h+var_C8], rax
0x18001df42  mov     [rsp+0F8h+var_D0], r10
0x18001df47  mov     [rsp+0F8h+var_D8], r11
0x18001df4c  call    cs:__imp_TraceMessage
0x18001df52  add     rsp, 0D8h
0x18001df59  pop     rdi
0x18001df5a  pop     rsi
0x18001df5b  pop     rbp
0x18001df5c  pop     rbx
0x18001df5d  retn
```
