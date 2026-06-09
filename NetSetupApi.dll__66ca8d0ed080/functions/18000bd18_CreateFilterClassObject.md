# CreateFilterClassObject

- ea: `0x18000bd18`
- end: `0x18000be1a`
- name: `CreateFilterClassObject`
- size: `258`
- prototype: `__int64 __fastcall(__int64, __int64, _OWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x18000be20`

## callees

- `0x18000ab5c`
- `0x18000bd18`
- `0x18000cba0`
- `0x18000f690`
- `0x1800119f0`

## pseudocode

```c
__int64 __fastcall CreateFilterClassObject(__int64 a1, __int64 a2, _OWORD *a3)
{
  int v4; // edi
  __int64 v5; // rax
  int Object; // eax
  int v7; // r8d
  unsigned int v8; // ebx
  __int64 result; // rax
  __int128 v10; // [rsp+30h] [rbp-50h] BYREF
  int v11; // [rsp+40h] [rbp-40h]
  int v12; // [rsp+44h] [rbp-3Ch]
  __int64 v13; // [rsp+48h] [rbp-38h]
  int v14; // [rsp+50h] [rbp-30h]
  int v15; // [rsp+54h] [rbp-2Ch]
  __int64 v16; // [rsp+58h] [rbp-28h]
  int v17[4]; // [rsp+60h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]

  v11 = 10;
  v4 = a2;
  v13 = 0;
  v10 = NETSETUPPKEY_FilterClass_Name;
  v12 = 0;
  v5 = -1;
  v14 = 18;
  v16 = a2;
  do
    ++v5;
  while ( *(_WORD *)(a2 + 2 * v5) );
  v15 = 2 * v5 + 2;
  *(_OWORD *)v17 = 0;
  Object = NetSetupCreateObject(a1, 13, 1, (__int64)&v10, (__int64)v17);
  v8 = Object;
  if ( Object >= 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      WPP_SF_S_guid_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, v7, v4, (__int64)v17);
    result = 0;
    *a3 = *(_OWORD *)v17;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x41,
      (int)"onecore\\net\\netsetup\\api\\filterclassapi.cpp",
      (const char *)(unsigned int)Object);
    return v8;
  }
  return result;
}

```

## disassembly

```asm
0x18000bd18  push    rbp
0x18000bd1a  push    rbx
0x18000bd1b  push    rsi
0x18000bd1c  push    rdi
0x18000bd1d  push    r14
0x18000bd1f  mov     rbp, rsp
0x18000bd22  sub     rsp, 80h
0x18000bd29  mov     rax, cs:__security_cookie
0x18000bd30  xor     rax, rsp
0x18000bd33  mov     [rbp+var_10], rax
0x18000bd37  mov     eax, cs:dword_18001EDA8
0x18000bd3d  xor     r14d, r14d
0x18000bd40  movups  xmm0, cs:NETSETUPPKEY_FilterClass_Name
0x18000bd47  mov     [rbp+var_40], eax
0x18000bd4a  mov     rsi, r8
0x18000bd4d  mov     rdi, rdx
0x18000bd50  mov     [rbp+var_38], r14
0x18000bd54  movups  [rbp+var_50], xmm0
0x18000bd58  mov     [rbp+var_3C], r14d
0x18000bd5c  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000bd60  mov     [rbp+var_30], 12h
0x18000bd67  mov     [rbp+var_28], rdx
0x18000bd6b  inc     rax
0x18000bd6e  cmp     [rdx+rax*2], r14w
0x18000bd73  jnz     short loc_18000BD6B
0x18000bd75  lea     eax, ds:2[rax*2]
0x18000bd7c  mov     edx, 0Dh
0x18000bd81  mov     [rbp+var_2C], eax
0x18000bd84  lea     r9, [rbp+var_50]
0x18000bd88  xorps   xmm0, xmm0
0x18000bd8b  lea     rax, [rbp+var_20]
0x18000bd8f  movups  xmmword ptr [rbp+var_20], xmm0
0x18000bd93  lea     r8d, [rdx-0Ch]
0x18000bd97  mov     qword ptr [rsp+80h+var_60], rax; int
0x18000bd9c  call    NetSetupCreateObject
0x18000bda1  mov     ebx, eax
0x18000bda3  test    eax, eax
0x18000bda5  jns     short loc_18000BDC3
0x18000bda7  mov     rcx, [rbp+28h]; this
0x18000bdab  lea     r8, aOnecoreNetNets; "onecore\\net\\netsetup\\api\\filterclas"...
0x18000bdb2  mov     r9d, eax; char *
0x18000bdb5  mov     edx, 41h ; 'A'; void *
0x18000bdba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000bdbf  mov     eax, ebx
0x18000bdc1  jmp     short loc_18000BE00
0x18000bdc3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bdca  lea     rax, WPP_GLOBAL_Control
0x18000bdd1  cmp     rcx, rax
0x18000bdd4  jz      short loc_18000BDF6
0x18000bdd6  cmp     byte ptr [rcx+19h], 4
0x18000bdda  jb      short loc_18000BDF6
0x18000bddc  mov     rcx, [rcx+10h]
0x18000bde0  lea     rax, [rbp+var_20]
0x18000bde4  mov     edx, 0Ch
0x18000bde9  mov     qword ptr [rsp+80h+var_60], rax
0x18000bdee  mov     r9, rdi
0x18000bdf1  call    WPP_SF_S_guid_
0x18000bdf6  movups  xmm0, xmmword ptr [rbp+var_20]
0x18000bdfa  xor     eax, eax
0x18000bdfc  movdqu  xmmword ptr [rsi], xmm0
0x18000be00  mov     rcx, [rbp+var_10]
0x18000be04  xor     rcx, rsp; StackCookie
0x18000be07  call    __security_check_cookie
0x18000be0c  add     rsp, 80h
0x18000be13  pop     r14
0x18000be15  pop     rdi
0x18000be16  pop     rsi
0x18000be17  pop     rbx
0x18000be18  pop     rbp
0x18000be19  retn
```
