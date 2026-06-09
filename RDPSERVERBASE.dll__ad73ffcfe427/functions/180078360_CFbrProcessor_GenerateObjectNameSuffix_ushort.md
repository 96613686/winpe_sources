# CFbrProcessor::GenerateObjectNameSuffix(ushort * *)

- ea: `0x180078360`
- end: `0x1800785f1`
- name: `?GenerateObjectNameSuffix@CFbrProcessor@@IEAAJPEAPEAG@Z`
- size: `657`
- prototype: `__int64 __fastcall(CFbrProcessor *__hidden this, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, reparse_path`

## callers

- `0x180078cd0`

## callees

- `0x18003b118`
- `0x180076090`
- `0x180078360`
- `0x180079724`
- `0x180079770`
- `0x18007e9e0`
- `0x18007f6a4`
- `0x18007f6b0`
- `0x1800ac9f4`

## import_xrefs

- `RPCRT4!UuidToStringW` at `0x18007841f`
- `RPCRT4!UuidToStringW` at `0x18007841f`
- `RPCRT4!RpcStringFreeW` at `0x1800785bb`
- `RPCRT4!RpcStringFreeW` at `0x1800785bb`
- `RPCRT4!UuidCreate` at `0x1800783a0`
- `RPCRT4!UuidCreate` at `0x1800783a0`

## string_xrefs

- `0x18007859e`: `StringCchCopyW failed.`

## pseudocode

```c
__int64 __fastcall CFbrProcessor::GenerateObjectNameSuffix(CFbrProcessor *this, unsigned __int16 **a2)
{
  unsigned __int16 *v2; // r14
  int v4; // ebx
  unsigned int v5; // esi
  unsigned int CurrentThreadActivityIdPrefix; // eax
  __int64 v7; // rdx
  unsigned int v8; // eax
  int v9; // edx
  const char *v10; // rcx
  unsigned __int64 v11; // rbx
  unsigned __int16 *v12; // rax
  unsigned int v13; // eax
  RPC_WSTR StringUuid; // [rsp+30h] [rbp-30h] BYREF
  unsigned __int64 v16; // [rsp+38h] [rbp-28h] BYREF
  UUID Uuid; // [rsp+40h] [rbp-20h] BYREF

  StringUuid = 0;
  v2 = 0;
  Uuid = 0;
  v16 = 0;
  v4 = UuidCreate(&Uuid);
  if ( v4 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      if ( v4 > 0 )
        v5 = (unsigned __int16)v4 | 0x80070000;
      else
        v5 = v4;
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v7 = 28;
LABEL_9:
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v7,
        WPP_d8ea9ca96d333cbf0b3b063f76d91f65_Traceguids,
        CurrentThreadActivityIdPrefix,
        v5);
      goto LABEL_10;
    }
    goto LABEL_10;
  }
  v4 = UuidToStringW(&Uuid, &StringUuid);
  if ( v4 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      if ( v4 > 0 )
        v5 = (unsigned __int16)v4 | 0x80070000;
      else
        v5 = v4;
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v7 = 29;
      goto LABEL_9;
    }
LABEL_10:
    if ( v4 > 0 )
      v4 = (unsigned __int16)v4 | 0x80070000;
    goto LABEL_38;
  }
  v4 = StringCchLengthW(StringUuid, 0x7FFFFFFFu, &v16);
  if ( v4 < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_38;
    }
    v8 = RdpWppGetCurrentThreadActivityIdPrefix();
    v9 = 30;
    v10 = "StringCchLengthW failed.";
LABEL_25:
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v9,
      (unsigned int)WPP_d8ea9ca96d333cbf0b3b063f76d91f65_Traceguids,
      v8,
      (__int64)v10,
      v4);
    goto LABEL_38;
  }
  v11 = (unsigned int)(v16 + 1);
  v12 = (unsigned __int16 *)operator new(saturated_mul(v11, 2u));
  v2 = v12;
  if ( v12 )
  {
    v4 = StringCchCopyW(v12, v11, StringUuid);
    if ( v4 >= 0 )
    {
      *a2 = v2;
      v2 = 0;
      goto LABEL_38;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v8 = RdpWppGetCurrentThreadActivityIdPrefix();
      v9 = 32;
      v10 = "StringCchCopyW failed.";
      goto LABEL_25;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v13 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        31,
        WPP_d8ea9ca96d333cbf0b3b063f76d91f65_Traceguids,
        v13,
        -2147024882);
    }
    v4 = -2147024882;
  }
LABEL_38:
  if ( StringUuid )
    RpcStringFreeW(&StringUuid);
  if ( v2 )
    operator delete(v2);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180078360  mov     [rsp-18h+arg_0], rbx
0x180078365  mov     [rsp-18h+arg_10], rsi
0x18007836a  push    rbp
0x18007836b  push    rdi
0x18007836c  push    r14
0x18007836e  mov     rbp, rsp
0x180078371  sub     rsp, 60h
0x180078375  mov     rax, cs:__security_cookie
0x18007837c  xor     rax, rsp
0x18007837f  mov     [rbp+var_10], rax
0x180078383  xorps   xmm0, xmm0
0x180078386  mov     [rbp+StringUuid], 0
0x18007838e  xor     r14d, r14d
0x180078391  lea     rcx, [rbp+Uuid]; Uuid
0x180078395  movups  xmmword ptr [rbp+Uuid.Data1], xmm0
0x180078399  mov     [rbp+var_28], r14
0x18007839d  mov     rdi, rdx
0x1800783a0  call    cs:__imp_UuidCreate
0x1800783a6  mov     ebx, eax
0x1800783a8  test    eax, eax
0x1800783aa  jz      short loc_180078417
0x1800783ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800783b3  lea     rax, WPP_GLOBAL_Control
0x1800783ba  mov     edi, 80070000h
0x1800783bf  cmp     rcx, rax
0x1800783c2  jz      short loc_180078405
0x1800783c4  test    byte ptr [rcx+1Ch], 8
0x1800783c8  jz      short loc_180078405
0x1800783ca  cmp     byte ptr [rcx+19h], 2
0x1800783ce  jb      short loc_180078405
0x1800783d0  test    ebx, ebx
0x1800783d2  jg      short loc_1800783D8
0x1800783d4  mov     esi, ebx
0x1800783d6  jmp     short loc_1800783DD
0x1800783d8  movzx   esi, bx
0x1800783db  or      esi, edi
0x1800783dd  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800783e2  mov     edx, 1Ch
0x1800783e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800783ee  lea     r8, WPP_d8ea9ca96d333cbf0b3b063f76d91f65_Traceguids
0x1800783f5  mov     r9d, eax
0x1800783f8  mov     dword ptr [rsp+60h+var_40], esi
0x1800783fc  mov     rcx, [rcx+10h]
0x180078400  call    WPP_SF_Dd
0x180078405  test    ebx, ebx
0x180078407  jle     loc_1800785B0
0x18007840d  movzx   ebx, bx
0x180078410  or      ebx, edi
0x180078412  jmp     loc_1800785B0
0x180078417  lea     rdx, [rbp+StringUuid]; StringUuid
0x18007841b  lea     rcx, [rbp+Uuid]; Uuid
0x18007841f  call    cs:__imp_UuidToStringW
0x180078425  mov     ebx, eax
0x180078427  test    eax, eax
0x180078429  jz      short loc_18007846B
0x18007842b  mov     rcx, cs:WPP_GLOBAL_Control
0x180078432  lea     rax, WPP_GLOBAL_Control
0x180078439  mov     edi, 80070000h
0x18007843e  cmp     rcx, rax
0x180078441  jz      short loc_180078405
0x180078443  test    byte ptr [rcx+1Ch], 8
0x180078447  jz      short loc_180078405
0x180078449  cmp     byte ptr [rcx+19h], 2
0x18007844d  jb      short loc_180078405
0x18007844f  test    ebx, ebx
0x180078451  jg      short loc_180078457
0x180078453  mov     esi, ebx
0x180078455  jmp     short loc_18007845C
0x180078457  movzx   esi, bx
0x18007845a  or      esi, edi
0x18007845c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180078461  mov     edx, 1Dh
0x180078466  jmp     loc_1800783E7
0x18007846b  mov     rcx, [rbp+StringUuid]; unsigned __int16 *
0x18007846f  lea     r8, [rbp+var_28]; unsigned __int64 *
0x180078473  mov     edx, 7FFFFFFFh; unsigned __int64
0x180078478  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18007847d  mov     ebx, eax
0x18007847f  test    eax, eax
0x180078481  jns     short loc_1800784E7
0x180078483  mov     rcx, cs:WPP_GLOBAL_Control
0x18007848a  lea     rax, WPP_GLOBAL_Control
0x180078491  cmp     rcx, rax
0x180078494  jz      loc_1800785B0
0x18007849a  test    byte ptr [rcx+1Ch], 8
0x18007849e  jz      loc_1800785B0
0x1800784a4  cmp     byte ptr [rcx+19h], 2
0x1800784a8  jb      loc_1800785B0
0x1800784ae  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800784b3  mov     edx, 1Eh
0x1800784b8  lea     rcx, aStringcchlengt; "StringCchLengthW failed."
0x1800784bf  mov     [rsp+60h+var_38], ebx
0x1800784c3  lea     r8, WPP_d8ea9ca96d333cbf0b3b063f76d91f65_Traceguids
0x1800784ca  mov     [rsp+60h+var_40], rcx
0x1800784cf  mov     r9d, eax
0x1800784d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800784d9  mov     rcx, [rcx+10h]
0x1800784dd  call    WPP_SF_DsD
0x1800784e2  jmp     loc_1800785B0
0x1800784e7  mov     ebx, dword ptr [rbp+var_28]
0x1800784ea  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800784f1  inc     ebx
0x1800784f3  mov     eax, 2
0x1800784f8  mul     rbx
0x1800784fb  cmovb   rax, rcx
0x1800784ff  mov     rcx, rax; Size
0x180078502  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180078507  mov     r14, rax
0x18007850a  test    rax, rax
0x18007850d  jnz     short loc_180078560
0x18007850f  mov     rcx, cs:WPP_GLOBAL_Control
0x180078516  lea     rax, WPP_GLOBAL_Control
0x18007851d  cmp     rcx, rax
0x180078520  jz      short loc_180078559
0x180078522  test    byte ptr [rcx+1Ch], 8
0x180078526  jz      short loc_180078559
0x180078528  cmp     byte ptr [rcx+19h], 2
0x18007852c  jb      short loc_180078559
0x18007852e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180078533  mov     rcx, cs:WPP_GLOBAL_Control
0x18007853a  lea     edx, [r14+1Fh]
0x18007853e  mov     r9d, eax
0x180078541  mov     dword ptr [rsp+60h+var_40], 8007000Eh
0x180078549  lea     r8, WPP_d8ea9ca96d333cbf0b3b063f76d91f65_Traceguids
0x180078550  mov     rcx, [rcx+10h]
0x180078554  call    WPP_SF_Dd
0x180078559  mov     ebx, 8007000Eh
0x18007855e  jmp     short loc_1800785B0
0x180078560  mov     r8, [rbp+StringUuid]; unsigned __int16 *
0x180078564  mov     rdx, rbx; unsigned __int64
0x180078567  mov     rcx, r14; unsigned __int16 *
0x18007856a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18007856f  mov     ebx, eax
0x180078571  test    eax, eax
0x180078573  jns     short loc_1800785AA
0x180078575  mov     rcx, cs:WPP_GLOBAL_Control
0x18007857c  lea     rax, WPP_GLOBAL_Control
0x180078583  cmp     rcx, rax
0x180078586  jz      short loc_1800785B0
0x180078588  test    byte ptr [rcx+1Ch], 8
0x18007858c  jz      short loc_1800785B0
0x18007858e  cmp     byte ptr [rcx+19h], 2
0x180078592  jb      short loc_1800785B0
0x180078594  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180078599  mov     edx, 20h ; ' '
0x18007859e  lea     rcx, aStringcchcopyw_0; "StringCchCopyW failed."
0x1800785a5  jmp     loc_1800784BF
0x1800785aa  mov     [rdi], r14
0x1800785ad  xor     r14d, r14d
0x1800785b0  cmp     [rbp+StringUuid], 0
0x1800785b5  jz      short loc_1800785C1
0x1800785b7  lea     rcx, [rbp+StringUuid]; String
0x1800785bb  call    cs:__imp_RpcStringFreeW
0x1800785c1  test    r14, r14
0x1800785c4  jz      short loc_1800785CE
0x1800785c6  mov     rcx, r14; Block
0x1800785c9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800785ce  mov     eax, ebx
0x1800785d0  mov     rcx, [rbp+var_10]
0x1800785d4  xor     rcx, rsp; StackCookie
0x1800785d7  call    __security_check_cookie
0x1800785dc  lea     r11, [rsp+60h+var_s0]
0x1800785e1  mov     rbx, [r11+20h]
0x1800785e5  mov     rsi, [r11+30h]
0x1800785e9  mov     rsp, r11
0x1800785ec  pop     r14
0x1800785ee  pop     rdi
0x1800785ef  pop     rbp
0x1800785f0  retn
```
