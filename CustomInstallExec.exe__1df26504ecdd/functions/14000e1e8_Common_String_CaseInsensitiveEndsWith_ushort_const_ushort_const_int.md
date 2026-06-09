# Common::String::CaseInsensitiveEndsWith(ushort const *,ushort const *,int *)

- ea: `0x14000e1e8`
- end: `0x14000e2c2`
- name: `?CaseInsensitiveEndsWith@String@Common@@SAJPEBG0PEAH@Z`
- size: `218`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140008ec8`

## callees

- `0x140003f68`
- `0x14000b854`
- `0x14000e1a4`
- `0x14000e1e8`
- `0x14000e6ac`

## string_xrefs

- `0x14000e232`: `onecore\base\appmodel\common\widestring.cpp`

## pseudocode

```c
__int64 __fastcall Common::String::CaseInsensitiveEndsWith(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        int *a3)
{
  int v4; // ebx
  __int64 v5; // rdx
  __int64 v7; // r11
  int v8; // ebx
  BOOL v9; // ecx
  const void *v10; // rsi
  const unsigned __int16 *v11; // r8
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  unsigned __int64 v13; // [rsp+38h] [rbp+10h] BYREF
  unsigned __int64 v14; // [rsp+48h] [rbp+20h] BYREF

  v14 = 0;
  v13 = 0;
  v4 = StringCchLengthW(a1, 0x3FFFFFFFu, &v14);
  if ( v4 < 0 )
  {
    v5 = 103;
LABEL_3:
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)v5,
      (int)"onecore\\base\\appmodel\\common\\widestring.cpp",
      (const char *)(unsigned int)v4);
    return (unsigned int)v4;
  }
  v4 = StringCchLengthW(L".MSI", 0x3FFFFFFFu, &v13);
  if ( v4 < 0 )
  {
    v5 = 104;
    goto LABEL_3;
  }
  v8 = v13;
  if ( (unsigned int)v13 <= (unsigned int)v14 )
  {
    v10 = (const void *)(v7 + 2LL * (unsigned int)(v14 - v13));
    v9 = !memcmp_0(v10, L".MSI", 2LL * (unsigned int)v13)
      || Common::String::CaseInsensitiveCompare((LPCWCH)v10, v8, v11, v8) == 0;
  }
  else
  {
    v9 = 0;
  }
  *a3 = v9;
  return 0;
}

```

## disassembly

```asm
0x14000e1e8  mov     rax, rsp
0x14000e1eb  mov     [rax+8], rbx
0x14000e1ef  mov     [rax+18h], rsi
0x14000e1f3  mov     [rax+10h], rdx
0x14000e1f7  push    rdi; int
0x14000e1f8  sub     rsp, 20h
0x14000e1fc  mov     esi, 3FFFFFFFh
0x14000e201  mov     qword ptr [rax+20h], 0
0x14000e209  mov     rdi, r8
0x14000e20c  mov     qword ptr [rax+10h], 0
0x14000e214  mov     edx, esi; unsigned __int64
0x14000e216  lea     r8, [rax+20h]; unsigned __int64 *
0x14000e21a  mov     r11, rcx
0x14000e21d  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x14000e222  mov     ebx, eax
0x14000e224  test    eax, eax
0x14000e226  jns     short loc_14000E245
0x14000e228  mov     edx, 67h ; 'g'; void *
0x14000e22d  mov     rcx, [rsp+28h]; this
0x14000e232  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appmodel\\common\\widest"...
0x14000e239  mov     r9d, ebx; char *
0x14000e23c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14000e241  mov     eax, ebx
0x14000e243  jmp     short loc_14000E2B2
0x14000e245  lea     r8, [rsp+28h+arg_8]; unsigned __int64 *
0x14000e24a  mov     rdx, rsi; unsigned __int64
0x14000e24d  lea     rcx, Buf2; ".MSI"
0x14000e254  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x14000e259  mov     ebx, eax
0x14000e25b  test    eax, eax
0x14000e25d  jns     short loc_14000E266
0x14000e25f  mov     edx, 68h ; 'h'
0x14000e264  jmp     short loc_14000E22D
0x14000e266  mov     ebx, dword ptr [rsp+28h+arg_8]
0x14000e26a  mov     eax, dword ptr [rsp+28h+arg_18]
0x14000e26e  cmp     ebx, eax
0x14000e270  jbe     short loc_14000E276
0x14000e272  xor     ecx, ecx
0x14000e274  jmp     short loc_14000E2AE
0x14000e276  sub     eax, ebx
0x14000e278  lea     rdx, Buf2; ".MSI"
0x14000e27f  mov     r8, rbx
0x14000e282  add     r8, r8; Size
0x14000e285  lea     rsi, [r11+rax*2]
0x14000e289  mov     rcx, rsi; Buf1
0x14000e28c  call    memcmp_0
0x14000e291  test    eax, eax
0x14000e293  jnz     short loc_14000E29A
0x14000e295  lea     ecx, [rax+1]
0x14000e298  jmp     short loc_14000E2AE
0x14000e29a  mov     r9d, ebx; unsigned int
0x14000e29d  mov     edx, ebx; unsigned int
0x14000e29f  mov     rcx, rsi; lpString1
0x14000e2a2  call    ?CaseInsensitiveCompare@String@Common@@SAHPEBGK0K@Z; Common::String::CaseInsensitiveCompare(ushort const *,ulong,ushort const *,ulong)
0x14000e2a7  xor     ecx, ecx
0x14000e2a9  test    eax, eax
0x14000e2ab  setz    cl
0x14000e2ae  mov     [rdi], ecx
0x14000e2b0  xor     eax, eax
0x14000e2b2  mov     rbx, [rsp+28h+arg_0]
0x14000e2b7  mov     rsi, [rsp+28h+arg_10]
0x14000e2bc  add     rsp, 20h
0x14000e2c0  pop     rdi
0x14000e2c1  retn
```
