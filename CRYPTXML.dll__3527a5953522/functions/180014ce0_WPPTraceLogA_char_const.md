# WPPTraceLogA(char const *,...)

- ea: `0x180014ce0`
- end: `0x180014df0`
- name: `?WPPTraceLogA@@YAXPEBDZZ`
- size: `272`
- prototype: `void(const char *, ...)`
- caller_count: `85`
- callee_count: `6`
- tags: ``

## callers

- `0x180001010`
- `0x1800013a0`
- `0x180001a40`
- `0x180001d00`
- `0x180001fe0`
- `0x180002470`
- `0x1800029b0`
- `0x1800031b0`
- `0x180003650`
- `0x180003fb0`
- `0x180004670`
- `0x1800049c0`
- `0x180004f90`
- `0x1800057a0`
- `0x180006150`
- `0x180006da0`
- `0x180007100`
- `0x180007180`
- `0x180007730`
- `0x180008000`
- `0x180008110`
- `0x1800084b0`
- `0x1800088d0`
- `0x180008b10`
- `0x180008dc0`
- `0x180008ffc`
- `0x180009180`
- `0x180009310`
- `0x1800094a0`
- `0x180009a10`
- `0x180009f80`
- `0x18000a310`
- `0x18000b1e0`
- `0x18000b3b0`
- `0x18000c2d0`
- `0x18000c75c`
- `0x18000c990`
- `0x18000cfb0`
- `0x18000d1f0`
- `0x18000d500`
- `0x18000e220`
- `0x18000e290`
- `0x18000e750`
- `0x18000edd0`
- `0x18000ee80`
- `0x18000f200`
- `0x18000f7d0`
- `0x18000fe50`
- `0x180010520`
- `0x180010730`

## callees

- `0x180008078`
- `0x180014ce0`
- `0x180015d34`
- `0x180015d88`
- `0x180018640`
- `0x180019010`

## pseudocode

```c
void WPPTraceLogA(const char *a1, ...)
{
  unsigned __int64 v1; // rdx
  void *v2; // rsp
  char *v3; // rbx
  _DWORD *v4; // rax
  __int64 v5; // rdx
  __int64 v6; // r8
  __int64 v7; // [rsp-20h] [rbp-230h] BYREF
  int v8; // [rsp+0h] [rbp-210h]
  _QWORD v9[66]; // [rsp+8h] [rbp-208h] BYREF
  __int64 v11; // [rsp+248h] [rbp+38h] BYREF
  va_list va; // [rsp+248h] [rbp+38h]
  __int64 v13; // [rsp+250h] [rbp+40h]
  va_list va1; // [rsp+258h] [rbp+48h] BYREF

  va_start(va1, a1);
  va_start(va, a1);
  v11 = va_arg(va1, _QWORD);
  v13 = va_arg(va1, _QWORD);
  if ( (unsigned __int64)g_ulMaxStackAllocSize >= 0x200
    && (unsigned __int64)(g_ulAdditionalProbeSize + 520) >= 0x200
    && (unsigned int)VerifyStackAvailable()
    && (v2 = alloca(528), &v7 != (__int64 *)-32LL)
    && (v8 = 1801679955, (v3 = (char *)v9) != 0)
    || (v4 = (_DWORD *)((__int64 (__fastcall *)(__int64))g_pfnAllocate)(520)) != 0
    && (*v4 = 1885431112, v3 = (char *)(v4 + 2), v4 != (_DWORD *)-8LL) )
  {
    v9[65] = 0;
    if ( (int)StringCbVPrintfA(v3, v1, a1, va) < 0 )
      goto LABEL_13;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), v5, v6, v3, v8);
    if ( v3 )
    {
LABEL_13:
      if ( *((_DWORD *)v3 - 2) == 1885431112 )
        ((void (*)(void))g_pfnFree)();
    }
  }
}

```

## disassembly

```asm
0x180014ce0  mov     rax, rsp
0x180014ce3  mov     [rax+8], rcx
0x180014ce7  mov     [rax+10h], rdx
0x180014ceb  mov     [rax+18h], r8
0x180014cef  mov     [rax+20h], r9
0x180014cf3  push    rbp
0x180014cf4  push    rbx
0x180014cf5  sub     rsp, 38h
0x180014cf9  lea     rbp, [rsp+20h]
0x180014cfe  mov     rax, cs:__security_cookie
0x180014d05  xor     rax, rbp
0x180014d08  mov     [rbp+20h+var_18], rax
0x180014d0c  mov     edx, 200h
0x180014d11  cmp     cs:g_ulMaxStackAllocSize, rdx
0x180014d18  jb      short loc_180014D59
0x180014d1a  mov     rcx, cs:g_ulAdditionalProbeSize
0x180014d21  add     rcx, 208h
0x180014d28  cmp     rcx, rdx
0x180014d2b  jb      short loc_180014D59
0x180014d2d  call    VerifyStackAvailable
0x180014d32  test    eax, eax
0x180014d34  jz      short loc_180014D59
0x180014d36  mov     eax, [rsp+40h+var_40]
0x180014d39  mov     eax, 210h
0x180014d3e  sub     rsp, rax
0x180014d41  lea     rbx, [rsp+250h+var_230]
0x180014d46  mov     eax, [rbx]
0x180014d48  test    rbx, rbx
0x180014d4b  jz      short loc_180014D59
0x180014d4d  mov     dword ptr [rbx], 6B637453h
0x180014d53  add     rbx, 8
0x180014d57  jnz     short loc_180014D7E
0x180014d59  mov     rax, cs:g_pfnAllocate
0x180014d60  mov     ecx, 208h
0x180014d65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014d6a  mov     rbx, rax
0x180014d6d  test    rax, rax
0x180014d70  jz      short loc_180014DDC
0x180014d72  mov     dword ptr [rax], 70616548h
0x180014d78  add     rbx, 8
0x180014d7c  jz      short loc_180014DDC
0x180014d7e  mov     r8, [rbp+20h+arg_0]; char *
0x180014d82  lea     r9, [rbp+20h+arg_8]; char *
0x180014d86  mov     rcx, rbx; char *
0x180014d89  mov     [rbp+20h+var_20], 0
0x180014d91  call    ?StringCbVPrintfA@@YAJPEAD_KPEBD0@Z; StringCbVPrintfA(char *,unsigned __int64,char const *,char *)
0x180014d96  test    eax, eax
0x180014d98  js      short loc_180014DC4
0x180014d9a  mov     rcx, cs:WPP_GLOBAL_Control
0x180014da1  lea     rax, WPP_GLOBAL_Control
0x180014da8  cmp     rcx, rax
0x180014dab  jz      short loc_180014DBF
0x180014dad  test    byte ptr [rcx+1Ch], 1
0x180014db1  jz      short loc_180014DBF
0x180014db3  mov     rcx, [rcx+10h]
0x180014db7  mov     r9, rbx
0x180014dba  call    WPP_SF_s
0x180014dbf  test    rbx, rbx
0x180014dc2  jz      short loc_180014DDC
0x180014dc4  lea     rcx, [rbx-8]
0x180014dc8  cmp     dword ptr [rcx], 70616548h
0x180014dce  jnz     short loc_180014DDC
0x180014dd0  mov     rax, cs:g_pfnFree
0x180014dd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014ddc  mov     rcx, [rbp+20h+var_18]
0x180014de0  xor     rcx, rbp; StackCookie
0x180014de3  call    __security_check_cookie
0x180014de8  lea     rsp, [rbp+18h]
0x180014dec  pop     rbx
0x180014ded  pop     rbp
0x180014dee  retn
```
