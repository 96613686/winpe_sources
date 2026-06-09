# CMsMpClientUtils::EnableSideBySideMode(ulong)

- ea: `0x180005390`
- end: `0x18000542a`
- name: `?EnableSideBySideMode@CMsMpClientUtils@@UEAAJK@Z`
- size: `154`
- prototype: `__int64 __fastcall(CMsMpClientUtils *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation`

## callees

- `0x180005390`
- `0x180005b0c`

## import_xrefs

- `mpclient!MpManagerOpen` at `0x1800053df`
- `mpclient!MpManagerOpen` at `0x1800053df`
- `mpclient!MpHandleClose` at `0x1800053f5`
- `mpclient!MpHandleClose` at `0x180005417`
- `mpclient!MpHandleClose` at `0x1800053f5`
- `mpclient!MpHandleClose` at `0x180005417`
- `mpclient!MpManagerEnable` at `0x180005401`
- `mpclient!MpManagerEnable` at `0x180005401`

## pseudocode

```c
__int64 __fastcall CMsMpClientUtils::EnableSideBySideMode(CMsMpClientUtils *this, unsigned int a2)
{
  int v3; // eax
  __int64 v4; // rcx
  unsigned int v5; // ebx
  int v7; // eax
  __int64 v8; // [rsp+40h] [rbp+8h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_sq(*((_QWORD *)WPP_GLOBAL_Control + 2), 26);
  v8 = 0;
  v3 = MpManagerOpen(0, &v8);
  v4 = v8;
  v5 = v3;
  if ( v3 < 0 || (v7 = MpManagerEnable(v8, a2), v4 = v8, v5 = v7, v7 < 0) )
  {
    if ( v4 )
      MpHandleClose(v4);
    return v5;
  }
  else
  {
    if ( v8 )
      MpHandleClose(v8);
    return 0;
  }
}

```

## disassembly

```asm
0x180005390  mov     [rsp+arg_8], rbx
0x180005395  push    rdi
0x180005396  sub     rsp, 30h
0x18000539a  mov     edi, edx
0x18000539c  mov     rax, rcx
0x18000539f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800053a6  lea     rdx, WPP_GLOBAL_Control
0x1800053ad  cmp     rcx, rdx
0x1800053b0  jz      short loc_1800053CF
0x1800053b2  test    byte ptr [rcx+1Ch], 8
0x1800053b6  jz      short loc_1800053CF
0x1800053b8  mov     rcx, [rcx+10h]
0x1800053bc  add     rax, 0FFFFFFFFFFFFFFC0h
0x1800053c0  mov     edx, 1Ah
0x1800053c5  mov     [rsp+38h+var_18], rax
0x1800053ca  call    WPP_SF_sq
0x1800053cf  lea     rdx, [rsp+38h+arg_0]
0x1800053d4  mov     [rsp+38h+arg_0], 0
0x1800053dd  xor     ecx, ecx
0x1800053df  call    cs:__imp_MpManagerOpen
0x1800053e5  mov     rcx, [rsp+38h+arg_0]
0x1800053ea  mov     ebx, eax
0x1800053ec  test    eax, eax
0x1800053ee  jns     short loc_1800053FF
0x1800053f0  test    rcx, rcx
0x1800053f3  jz      short loc_1800053FB
0x1800053f5  call    cs:__imp_MpHandleClose
0x1800053fb  mov     eax, ebx
0x1800053fd  jmp     short loc_18000541F
0x1800053ff  mov     edx, edi
0x180005401  call    cs:__imp_MpManagerEnable
0x180005407  mov     rcx, [rsp+38h+arg_0]
0x18000540c  mov     ebx, eax
0x18000540e  test    eax, eax
0x180005410  js      short loc_1800053F0
0x180005412  test    rcx, rcx
0x180005415  jz      short loc_18000541D
0x180005417  call    cs:__imp_MpHandleClose
0x18000541d  xor     eax, eax
0x18000541f  mov     rbx, [rsp+38h+arg_8]
0x180005424  add     rsp, 30h
0x180005428  pop     rdi
0x180005429  retn
```
