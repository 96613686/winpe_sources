# DmIsDeviceRoaming(int *)

- ea: `0x180063290`
- end: `0x18006347e`
- name: `?DmIsDeviceRoaming@@YAJPEAH@Z`
- size: `494`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180063290`

## import_xrefs

- `ext-ms-win-wwan-wwapi-l1-1-0!WwanQueryInterface` at `0x1800633cc`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanQueryInterface` at `0x18006342c`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanQueryInterface` at `0x1800633cc`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanQueryInterface` at `0x18006342c`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x180063341`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x180063341`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x1800632cc`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x1800632cc`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x180063300`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x180063315`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18006332a`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x1800633e6`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18006344e`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x180063300`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x180063315`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18006332a`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x1800633e6`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18006344e`
- `ext-ms-win-wwan-wwapi-l1-1-1!WwanEnumerateInterfaces` at `0x180063369`
- `ext-ms-win-wwan-wwapi-l1-1-1!WwanEnumerateInterfaces` at `0x180063369`

## pseudocode

```c
__int64 __fastcall DmIsDeviceRoaming(int *a1)
{
  signed int v2; // eax
  unsigned int v3; // edi
  bool v4; // cc
  unsigned int i; // esi
  __int64 v7; // r15
  bool v8; // cc
  int v9; // ebx
  unsigned int *v10; // [rsp+40h] [rbp-10h] BYREF
  int *v11; // [rsp+48h] [rbp-8h] BYREF
  int v12; // [rsp+90h] [rbp+40h] BYREF
  int v13; // [rsp+98h] [rbp+48h] BYREF
  __int64 v14; // [rsp+A0h] [rbp+50h] BYREF
  __int64 v15; // [rsp+A8h] [rbp+58h] BYREF

  *a1 = 0;
  v13 = 0;
  v14 = 0;
  v10 = 0;
  v15 = 0;
  v11 = 0;
  v2 = WwanOpenHandle(1, 0, &v13, &v14);
  v3 = v2;
  if ( v2 == 1062 )
  {
    v3 = 1;
  }
  else
  {
    v4 = v2 <= 0;
    if ( v2 || (v2 = WwanEnumerateInterfaces(v14, 0, &v10), v3 = v2, v4 = v2 <= 0, v2) )
    {
      if ( !v4 )
LABEL_5:
        v3 = (unsigned __int16)v2 | 0x80070000;
    }
    else
    {
      v3 = 0;
      for ( i = 0; i < *v10; ++i )
      {
        v7 = 147LL * i;
        v12 = 0;
        v2 = WwanQueryInterface(v14, &v10[v7 + 1], 28, 0, &v12, &v11, 0, 0);
        v8 = v2 <= 0;
        if ( v2 )
          goto LABEL_25;
        v9 = *v11;
        WwanFreeMemory();
        v11 = 0;
        if ( v9 )
        {
          v2 = WwanQueryInterface(v14, &v10[v7 + 1], 7, 0, &v12, &v15, 0, 0);
          v8 = v2 <= 0;
          if ( v2 )
          {
LABEL_25:
            if ( !v8 )
              goto LABEL_5;
            v3 = v2;
            break;
          }
          if ( (unsigned int)(*(_DWORD *)(v15 + 1444) - 4) <= 1 )
          {
            *a1 = 1;
            break;
          }
          WwanFreeMemory();
          v15 = 0;
        }
      }
    }
  }
  if ( v15 )
    WwanFreeMemory();
  if ( v10 )
    WwanFreeMemory();
  if ( v11 )
    WwanFreeMemory();
  if ( v14 )
    WwanCloseHandle(v14, 0);
  return v3;
}

```

## disassembly

```asm
0x180063290  push    rbp
0x180063292  push    rbx
0x180063293  push    rsi
0x180063294  push    rdi
0x180063295  push    r12
0x180063297  push    r14
0x180063299  push    r15
0x18006329b  mov     rbp, rsp
0x18006329e  sub     rsp, 50h
0x1800632a2  xor     r12d, r12d
0x1800632a5  lea     r9, [rbp+arg_10]
0x1800632a9  xor     edx, edx
0x1800632ab  mov     [rcx], r12d
0x1800632ae  mov     r14, rcx
0x1800632b1  mov     [rbp+arg_8], r12d
0x1800632b5  lea     r8, [rbp+arg_8]
0x1800632b9  mov     [rbp+arg_10], r12
0x1800632bd  mov     [rbp+var_10], r12
0x1800632c1  lea     ecx, [rdx+1]
0x1800632c4  mov     [rbp+arg_18], r12
0x1800632c8  mov     [rbp+var_8], r12
0x1800632cc  call    cs:__imp_WwanOpenHandle
0x1800632d3  nop     dword ptr [rax+rax+00h]
0x1800632d8  mov     edi, eax
0x1800632da  cmp     eax, 426h
0x1800632df  jnz     short loc_1800632E8
0x1800632e1  lea     edi, [r12+1]
0x1800632e6  jmp     short loc_1800632F7
0x1800632e8  test    eax, eax
0x1800632ea  jz      short loc_18006335F
0x1800632ec  jle     short loc_1800632F7
0x1800632ee  movzx   edi, ax
0x1800632f1  or      edi, 80070000h
0x1800632f7  mov     rcx, [rbp+arg_18]
0x1800632fb  test    rcx, rcx
0x1800632fe  jz      short loc_18006330C
0x180063300  call    cs:__imp_WwanFreeMemory
0x180063307  nop     dword ptr [rax+rax+00h]
0x18006330c  mov     rcx, [rbp+var_10]
0x180063310  test    rcx, rcx
0x180063313  jz      short loc_180063321
0x180063315  call    cs:__imp_WwanFreeMemory
0x18006331c  nop     dword ptr [rax+rax+00h]
0x180063321  mov     rcx, [rbp+var_8]
0x180063325  test    rcx, rcx
0x180063328  jz      short loc_180063336
0x18006332a  call    cs:__imp_WwanFreeMemory
0x180063331  nop     dword ptr [rax+rax+00h]
0x180063336  mov     rcx, [rbp+arg_10]
0x18006333a  test    rcx, rcx
0x18006333d  jz      short loc_18006334D
0x18006333f  xor     edx, edx
0x180063341  call    cs:__imp_WwanCloseHandle
0x180063348  nop     dword ptr [rax+rax+00h]
0x18006334d  mov     eax, edi
0x18006334f  add     rsp, 50h
0x180063353  pop     r15
0x180063355  pop     r14
0x180063357  pop     r12
0x180063359  pop     rdi
0x18006335a  pop     rsi
0x18006335b  pop     rbx
0x18006335c  pop     rbp
0x18006335d  retn
0x18006335f  mov     rcx, [rbp+arg_10]
0x180063363  lea     r8, [rbp+var_10]
0x180063367  xor     edx, edx
0x180063369  call    cs:__imp_WwanEnumerateInterfaces
0x180063370  nop     dword ptr [rax+rax+00h]
0x180063375  mov     edi, eax
0x180063377  test    eax, eax
0x180063379  jnz     loc_1800632EC
0x18006337f  mov     edi, r12d
0x180063382  mov     esi, r12d
0x180063385  mov     rcx, [rbp+var_10]
0x180063389  cmp     esi, [rcx]
0x18006338b  jnb     loc_1800632F7
0x180063391  mov     [rsp+50h+var_18], r12
0x180063396  lea     rdx, [rcx+4]
0x18006339a  mov     rcx, [rbp+arg_10]
0x18006339e  xor     r9d, r9d
0x1800633a1  mov     eax, esi
0x1800633a3  imul    r15, rax, 24Ch
0x1800633aa  lea     rax, [rbp+var_8]
0x1800633ae  mov     [rsp+50h+var_20], r12
0x1800633b3  mov     [rsp+50h+var_28], rax
0x1800633b8  lea     r8d, [r9+1Ch]
0x1800633bc  lea     rax, [rbp+arg_0]
0x1800633c0  mov     [rbp+arg_0], r12d
0x1800633c4  add     rdx, r15
0x1800633c7  mov     [rsp+50h+var_30], rax
0x1800633cc  call    cs:__imp_WwanQueryInterface
0x1800633d3  nop     dword ptr [rax+rax+00h]
0x1800633d8  test    eax, eax
0x1800633da  jnz     loc_180063471
0x1800633e0  mov     rcx, [rbp+var_8]
0x1800633e4  mov     ebx, [rcx]
0x1800633e6  call    cs:__imp_WwanFreeMemory
0x1800633ed  nop     dword ptr [rax+rax+00h]
0x1800633f2  mov     [rbp+var_8], r12
0x1800633f6  test    ebx, ebx
0x1800633f8  jz      short loc_18006345E
0x1800633fa  mov     rdx, [rbp+var_10]
0x1800633fe  lea     rax, [rbp+arg_18]
0x180063402  mov     rcx, [rbp+arg_10]
0x180063406  xor     r9d, r9d
0x180063409  mov     [rsp+50h+var_18], r12
0x18006340e  add     rdx, 4
0x180063412  mov     [rsp+50h+var_20], r12
0x180063417  add     rdx, r15
0x18006341a  mov     [rsp+50h+var_28], rax
0x18006341f  lea     rax, [rbp+arg_0]
0x180063423  lea     r8d, [r9+7]
0x180063427  mov     [rsp+50h+var_30], rax
0x18006342c  call    cs:__imp_WwanQueryInterface
0x180063433  nop     dword ptr [rax+rax+00h]
0x180063438  test    eax, eax
0x18006343a  jnz     short loc_180063471
0x18006343c  mov     rcx, [rbp+arg_18]
0x180063440  mov     eax, [rcx+5A4h]
0x180063446  sub     eax, 4
0x180063449  cmp     eax, 1
0x18006344c  jbe     short loc_180063465
0x18006344e  call    cs:__imp_WwanFreeMemory
0x180063455  nop     dword ptr [rax+rax+00h]
0x18006345a  mov     [rbp+arg_18], r12
0x18006345e  inc     esi
0x180063460  jmp     loc_180063385
0x180063465  mov     dword ptr [r14], 1
0x18006346c  jmp     loc_1800632F7
0x180063471  jg      loc_1800632EE
0x180063477  mov     edi, eax
0x180063479  jmp     loc_1800632F7
```
