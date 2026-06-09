# CIPSecurity::AddToList(int,int,char *)

- ea: `0x18000e1f8`
- end: `0x18000e2d8`
- name: `?AddToList@CIPSecurity@@QEAAHHHPEAD@Z`
- size: `224`
- prototype: `int(CIPSecurity *__hidden this, int, int, char *)`
- caller_count: `4`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000f040`
- `0x18000f1e0`
- `0x18000f3b0`
- `0x18000f560`

## callees

- `0x18000e1f8`
- `0x18000e508`
- `0x18000e734`
- `0x18001c5f0`
- `0x18001c8b0`
- `0x18001d682`

## import_xrefs

- `msvcrt!strstr` at `0x18000e22a`
- `msvcrt!strstr` at `0x18000e22a`

## pseudocode

```c
__int64 __fastcall CIPSecurity::AddToList(CIPSecurity *this, int a2, int a3, char *a4)
{
  char *v8; // rax
  char *v9; // rcx
  char *v10; // rbx
  unsigned __int8 *Ip; // rdi
  unsigned __int8 *v12; // rax
  unsigned int v13; // r8d
  unsigned __int8 *v14; // rbx
  unsigned int v15; // esi
  int v16; // eax
  char *v17; // r8

  if ( a2 )
  {
    if ( a2 == 1 )
    {
      v8 = strstr(a4, ",");
      v9 = "255.255.255.255";
      v10 = v8;
      if ( v8 )
        v9 = v8 + 1;
      Ip = GetIp(v9);
      if ( v10 )
        *v10 = 0;
      v12 = GetIp(a4);
      v14 = v12;
      if ( Ip && v12 )
        v15 = ADDRESS_CHECK::AddAddr((CIPSecurity *)((char *)this + 24), a3, v13, Ip, v12);
      else
        v15 = 0;
      FreeIp(Ip);
      FreeIp(v14);
      return v15;
    }
    else
    {
      return 0;
    }
  }
  else
  {
    v16 = strncmp_0(a4, "*.", 2u);
    v17 = a4 + 2;
    if ( v16 )
      v17 = a4;
    return ADDRESS_CHECK::AddName((CIPSecurity *)((char *)this + 24), a3, v17, v16 != 0 ? 0x80000000 : 0);
  }
}

```

## disassembly

```asm
0x18000e1f8  push    rbx
0x18000e1fa  push    rbp
0x18000e1fb  push    rsi
0x18000e1fc  push    rdi
0x18000e1fd  push    r14
0x18000e1ff  sub     rsp, 30h
0x18000e203  mov     rsi, r9
0x18000e206  mov     ebp, r8d
0x18000e209  mov     r14, rcx
0x18000e20c  test    edx, edx
0x18000e20e  jz      loc_18000E295
0x18000e214  cmp     edx, 1
0x18000e217  jz      short loc_18000E220
0x18000e219  xor     eax, eax
0x18000e21b  jmp     loc_18000E2CD
0x18000e220  lea     rdx, asc_1800211E4; ","
0x18000e227  mov     rcx, rsi; Str
0x18000e22a  call    cs:__imp_strstr
0x18000e230  lea     rcx, a255255255255; "255.255.255.255"
0x18000e237  mov     rbx, rax
0x18000e23a  test    rax, rax
0x18000e23d  jz      short loc_18000E243
0x18000e23f  lea     rcx, [rax+1]; Buffer
0x18000e243  call    ?GetIp@@YAPEAEPEAD@Z; GetIp(char *)
0x18000e248  mov     rdi, rax
0x18000e24b  test    rbx, rbx
0x18000e24e  jz      short loc_18000E253
0x18000e250  mov     byte ptr [rbx], 0
0x18000e253  mov     rcx, rsi; Buffer
0x18000e256  call    ?GetIp@@YAPEAEPEAD@Z; GetIp(char *)
0x18000e25b  mov     rbx, rax
0x18000e25e  test    rdi, rdi
0x18000e261  jz      short loc_18000E27F
0x18000e263  test    rax, rax
0x18000e266  jz      short loc_18000E27F
0x18000e268  lea     rcx, [r14+18h]; this
0x18000e26c  mov     [rsp+58h+var_38], rax; unsigned __int8 *
0x18000e271  mov     r9, rdi; unsigned __int8 *
0x18000e274  mov     edx, ebp; int
0x18000e276  call    ?AddAddr@ADDRESS_CHECK@@QEAAHHKPEAE0@Z; ADDRESS_CHECK::AddAddr(int,ulong,uchar *,uchar *)
0x18000e27b  mov     esi, eax
0x18000e27d  jmp     short loc_18000E281
0x18000e27f  xor     esi, esi
0x18000e281  mov     rcx, rdi; unsigned __int8 *
0x18000e284  call    ?FreeIp@@YAHPEAE@Z; FreeIp(uchar *)
0x18000e289  mov     rcx, rbx; unsigned __int8 *
0x18000e28c  call    ?FreeIp@@YAHPEAE@Z; FreeIp(uchar *)
0x18000e291  mov     eax, esi
0x18000e293  jmp     short loc_18000E2CD
0x18000e295  mov     r8d, 2; MaxCount
0x18000e29b  lea     rdx, Str2; "*."
0x18000e2a2  mov     rcx, rsi; Str1
0x18000e2a5  call    strncmp_0
0x18000e2aa  mov     ecx, eax
0x18000e2ac  lea     r8, [rsi+2]
0x18000e2b0  neg     ecx
0x18000e2b2  mov     edx, ebp; int
0x18000e2b4  lea     rcx, [r14+18h]; this
0x18000e2b8  sbb     r9d, r9d
0x18000e2bb  and     r9d, 80000000h; unsigned int
0x18000e2c2  test    eax, eax
0x18000e2c4  cmovnz  r8, rsi; char *
0x18000e2c8  call    ?AddName@ADDRESS_CHECK@@QEAAHHPEADK@Z; ADDRESS_CHECK::AddName(int,char *,ulong)
0x18000e2cd  add     rsp, 30h
0x18000e2d1  pop     r14
0x18000e2d3  pop     rdi
0x18000e2d4  pop     rsi
0x18000e2d5  pop     rbp
0x18000e2d6  pop     rbx
0x18000e2d7  retn
```
