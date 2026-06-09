# UpdateAttributeMask(ushort const *,ulong *)

- ea: `0x140005af0`
- end: `0x140005bd8`
- name: `?UpdateAttributeMask@@YAXPEBGPEAK@Z`
- size: `232`
- prototype: `void __fastcall(wchar_t *Str, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x14000414c`

## callees

- `0x140005af0`
- `0x140007240`

## import_xrefs

- `msvcrt!wcsstr` at `0x140005b80`
- `msvcrt!wcsstr` at `0x140005b80`

## string_xrefs

- `0x140005b05`: `APPID://PATH`

## pseudocode

```c
void __fastcall UpdateAttributeMask(wchar_t *Str, unsigned int *a2)
{
  __int64 v4; // rbx
  int v5; // esi
  const wchar_t *v6; // r14
  int v7; // r8d
  wchar_t *SubStr; // [rsp+30h] [rbp-29h]
  _DWORD v9[2]; // [rsp+38h] [rbp-21h]
  const wchar_t *v10; // [rsp+40h] [rbp-19h]
  int v11; // [rsp+48h] [rbp-11h]
  const wchar_t *v12; // [rsp+50h] [rbp-9h]
  int v13; // [rsp+58h] [rbp-1h]
  const wchar_t *v14; // [rsp+60h] [rbp+7h]
  int v15; // [rsp+68h] [rbp+Fh]
  const wchar_t *v16; // [rsp+70h] [rbp+17h]
  int v17; // [rsp+78h] [rbp+1Fh]

  v9[0] = 1;
  SubStr = L"APPID://PATH";
  v11 = 2;
  v10 = L"APPID://SHA256FLATHASH";
  v13 = 4;
  v12 = L"APPID://SHA1HASH";
  v4 = 0;
  v15 = 8;
  v14 = L"APPID://SHA256HASH";
  v16 = L"APPID://FQBN";
  v17 = 16;
  do
  {
    v5 = v9[4 * v4];
    if ( (v5 & *a2) == 0 )
    {
      v6 = *(const wchar_t **)&v9[4 * v4 - 2];
      if ( wcsstr(Str, v6) )
      {
        *a2 |= v5;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
          WPP_SF_SS(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, v7, (_DWORD)v6, (__int64)Str);
      }
    }
    ++v4;
  }
  while ( v4 != 5 );
}

```

## disassembly

```asm
0x140005af0  push    rbp
0x140005af2  push    rbx
0x140005af3  push    rsi
0x140005af4  push    rdi
0x140005af5  push    r14
0x140005af7  push    r15
0x140005af9  lea     rbp, [rsp-2Fh]
0x140005afe  sub     rsp, 88h
0x140005b05  lea     rax, aAppidPath; "APPID://PATH"
0x140005b0c  mov     [rbp+57h+var_78], 1
0x140005b13  mov     [rbp+57h+SubStr], rax
0x140005b17  mov     rdi, rdx
0x140005b1a  lea     rax, aAppidSha256fla; "APPID://SHA256FLATHASH"
0x140005b21  mov     [rbp+57h+var_68], 2
0x140005b28  mov     [rbp+57h+var_70], rax
0x140005b2c  mov     r15, rcx
0x140005b2f  lea     rax, aAppidSha1hash; "APPID://SHA1HASH"
0x140005b36  mov     [rbp+57h+var_58], 4
0x140005b3d  mov     [rbp+57h+var_60], rax
0x140005b41  xor     ebx, ebx
0x140005b43  lea     rax, aAppidSha256has; "APPID://SHA256HASH"
0x140005b4a  mov     [rbp+57h+var_48], 8
0x140005b51  mov     [rbp+57h+var_50], rax
0x140005b55  lea     rax, aAppidFqbn; "APPID://FQBN"
0x140005b5c  mov     [rbp+57h+var_40], rax
0x140005b60  mov     [rbp+57h+var_38], 10h
0x140005b67  mov     rax, rbx
0x140005b6a  add     rax, rax
0x140005b6d  mov     esi, [rbp+rax*8+57h+var_78]
0x140005b71  test    [rdi], esi
0x140005b73  jnz     short loc_140005BBF
0x140005b75  mov     r14, [rbp+rax*8+57h+SubStr]
0x140005b7a  mov     rcx, r15; Str
0x140005b7d  mov     rdx, r14; SubStr
0x140005b80  call    cs:__imp_wcsstr
0x140005b86  test    rax, rax
0x140005b89  jz      short loc_140005BBF
0x140005b8b  or      [rdi], esi
0x140005b8d  mov     rcx, cs:WPP_GLOBAL_Control
0x140005b94  lea     rax, WPP_GLOBAL_Control
0x140005b9b  cmp     rcx, rax
0x140005b9e  jz      short loc_140005BBF
0x140005ba0  test    dword ptr [rcx+1Ch], 800h
0x140005ba7  jz      short loc_140005BBF
0x140005ba9  mov     rcx, [rcx+10h]
0x140005bad  mov     edx, 35h ; '5'
0x140005bb2  mov     r9, r14
0x140005bb5  mov     [rsp+0B0h+var_90], r15
0x140005bba  call    WPP_SF_SS
0x140005bbf  inc     rbx
0x140005bc2  cmp     rbx, 5
0x140005bc6  jnz     short loc_140005B67
0x140005bc8  add     rsp, 88h
0x140005bcf  pop     r15
0x140005bd1  pop     r14
0x140005bd3  pop     rdi
0x140005bd4  pop     rsi
0x140005bd5  pop     rbx
0x140005bd6  pop     rbp
0x140005bd7  retn
```
