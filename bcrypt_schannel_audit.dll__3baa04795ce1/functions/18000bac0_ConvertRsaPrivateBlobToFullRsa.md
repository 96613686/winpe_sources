# ConvertRsaPrivateBlobToFullRsa

- ea: `0x18000bac0`
- end: `0x18000bb99`
- name: `ConvertRsaPrivateBlobToFullRsa`
- size: `217`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000b824`
- `0x18000e628`

## callees

- `0x180005060`
- `0x180007a7c`
- `0x18000bac0`

## import_xrefs

- `bcryptPrimitives!MSCryptConvertRsaPrivateBlobToFullRsaBlob` at `0x18000bb35`
- `bcryptPrimitives!MSCryptConvertRsaPrivateBlobToFullRsaBlob` at `0x18000bb35`

## string_xrefs

- `0x18000bb09`: `onecore\ds\security\cryptoapi\ncrypt\translate\bcrypttranslate.c`
- `0x18000bb67`: `onecore\ds\security\cryptoapi\ncrypt\translate\bcrypttranslate.c`

## pseudocode

```c
__int64 __fastcall ConvertRsaPrivateBlobToFullRsa(_DWORD *a1, unsigned int a2, __int64 a3)
{
  __int64 v3; // rdi
  unsigned int v4; // r11d
  unsigned int v5; // ebx
  unsigned int v6; // r10d
  unsigned int v7; // ebx

  v3 = a3;
  v4 = a1[2] + 24;
  v5 = a2;
  if ( a1[2] >= 0xFFFFFFE8
    || (v6 = v4 + a1[3], v6 < v4)
    || (LODWORD(a3) = v6 + a1[4], (unsigned int)a3 < v6)
    || (a2 = a3 + a1[5], a2 < (unsigned int)a3) )
  {
    v7 = 534;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        a2,
        a3,
        (unsigned int)"Status",
        22,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\translate\\bcrypttranslate.c",
        161);
  }
  else if ( v5 >= a2 )
  {
    return (unsigned int)MSCryptConvertRsaPrivateBlobToFullRsaBlob(a1, v5, v3);
  }
  else
  {
    v7 = -2146893819;
    DebugTraceError(2148073477LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\translate\\bcrypttranslate.c");
  }
  return v7;
}

```

## disassembly

```asm
0x18000bac0  mov     [rsp+arg_0], rbx
0x18000bac5  push    rdi
0x18000bac6  sub     rsp, 40h
0x18000baca  mov     r11d, [rcx+8]
0x18000bace  mov     rdi, r8
0x18000bad1  add     r11d, 18h
0x18000bad5  mov     ebx, edx
0x18000bad7  cmp     r11d, 18h
0x18000badb  jb      short loc_18000BB45
0x18000badd  mov     r10d, [rcx+0Ch]
0x18000bae1  add     r10d, r11d
0x18000bae4  cmp     r10d, r11d
0x18000bae7  jb      short loc_18000BB45
0x18000bae9  mov     r8d, [rcx+10h]
0x18000baed  add     r8d, r10d
0x18000baf0  cmp     r8d, r10d
0x18000baf3  jb      short loc_18000BB45
0x18000baf5  mov     edx, [rcx+14h]
0x18000baf8  add     edx, r8d
0x18000bafb  cmp     edx, r8d
0x18000bafe  jb      short loc_18000BB45
0x18000bb00  cmp     ebx, edx
0x18000bb02  jnb     short loc_18000BB26
0x18000bb04  mov     ebx, 80090005h
0x18000bb09  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000bb10  mov     ecx, ebx
0x18000bb12  lea     rdx, aStatus; "Status"
0x18000bb19  mov     r9d, 4A8h
0x18000bb1f  call    DebugTraceError
0x18000bb24  jmp     short loc_18000BB8B
0x18000bb26  mov     rax, [rsp+48h+arg_20]
0x18000bb2b  mov     r8, rdi
0x18000bb2e  mov     edx, ebx
0x18000bb30  mov     [rsp+48h+var_28], rax
0x18000bb35  call    cs:__imp_MSCryptConvertRsaPrivateBlobToFullRsaBlob
0x18000bb3c  nop     dword ptr [rax+rax+00h]
0x18000bb41  mov     ebx, eax
0x18000bb43  jmp     short loc_18000BB8B
0x18000bb45  mov     ebx, 216h
0x18000bb4a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bb51  lea     rax, WPP_GLOBAL_Control
0x18000bb58  cmp     rcx, rax
0x18000bb5b  jz      short loc_18000BB8B
0x18000bb5d  test    byte ptr [rcx+1Ch], 1
0x18000bb61  jz      short loc_18000BB8B
0x18000bb63  mov     rcx, [rcx+10h]
0x18000bb67  lea     rax, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000bb6e  mov     [rsp+48h+var_18], 4A1h
0x18000bb76  lea     r9, aStatus; "Status"
0x18000bb7d  mov     [rsp+48h+var_20], rax
0x18000bb82  mov     dword ptr [rsp+48h+var_28], ebx
0x18000bb86  call    WPP_SF_sDsd
0x18000bb8b  mov     eax, ebx
0x18000bb8d  mov     rbx, [rsp+48h+arg_0]
0x18000bb92  add     rsp, 40h
0x18000bb96  pop     rdi
0x18000bb97  retn
```
