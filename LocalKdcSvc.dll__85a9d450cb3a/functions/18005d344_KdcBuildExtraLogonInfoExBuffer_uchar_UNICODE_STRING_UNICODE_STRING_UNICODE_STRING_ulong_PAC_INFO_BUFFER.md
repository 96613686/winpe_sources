# KdcBuildExtraLogonInfoExBuffer(uchar,_UNICODE_STRING *,_UNICODE_STRING *,_UNICODE_STRING *,ulong,_PAC_INFO_BUFFER * *)

- ea: `0x18005d344`
- end: `0x18005d56b`
- name: `?KdcBuildExtraLogonInfoExBuffer@@YAJEPEAU_UNICODE_STRING@@00KPEAPEAU_PAC_INFO_BUFFER@@@Z`
- size: `551`
- prototype: `__int64 __fastcall(char, struct _UNICODE_STRING *, struct _UNICODE_STRING *, struct _UNICODE_STRING *, unsigned int, struct _PAC_INFO_BUFFER **)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18005c560`

## callees

- `0x180002ad0`
- `0x1800038f0`
- `0x180003908`
- `0x18001cdc4`
- `0x18005a060`
- `0x18005d344`

## import_xrefs

- `ntdll!RtlLengthSid` at `0x18005d3f4`
- `ntdll!RtlLengthSid` at `0x18005d51e`
- `ntdll!RtlLengthSid` at `0x18005d3f4`
- `ntdll!RtlLengthSid` at `0x18005d51e`

## pseudocode

```c
__int64 __fastcall KdcBuildExtraLogonInfoExBuffer(
        char a1,
        struct _UNICODE_STRING *a2,
        struct _UNICODE_STRING *a3,
        struct _UNICODE_STRING *a4,
        unsigned int a5,
        struct _PAC_INFO_BUFFER **a6)
{
  unsigned int Length; // eax
  unsigned int v11; // r8d
  unsigned int v12; // eax
  unsigned int v13; // ecx
  unsigned int v14; // eax
  unsigned int v15; // edx
  unsigned int v16; // eax
  unsigned int v17; // ebx
  unsigned int v18; // ecx
  unsigned int v19; // ebx
  struct _PAC_INFO_BUFFER *v20; // rax
  char *v22; // rdi
  char *v23; // rbx
  char *v24; // rbx
  char *v25; // rbx
  unsigned __int16 v26; // ax
  _BYTE Sid[80]; // [rsp+20h] [rbp-98h] BYREF

  memset_0(Sid, 0, 0x48u);
  KdcMakeAccountSid(Sid, a5);
  Length = a2->Length;
  v11 = (Length + 7) & 0xFFFFFFF8;
  if ( Length > v11 )
    return 3221225621LL;
  v12 = a3->Length;
  v13 = (v12 + 7) & 0xFFFFFFF8;
  if ( v12 > v13 )
    return 3221225621LL;
  v14 = a4->Length;
  v15 = (v14 + 7) & 0xFFFFFFF8;
  if ( v14 > v15 )
    return 3221225621LL;
  v16 = v13 + v11;
  if ( v13 + v11 < v11 )
    return 3221225621LL;
  v17 = v16 + v15;
  if ( v16 + v15 < v16 )
    return 3221225621LL;
  v18 = v17 + ((RtlLengthSid(Sid) + 7) & 0xFFFFFFF8);
  if ( v18 < v17 )
    return 3221225621LL;
  v19 = v18 + 40;
  if ( v18 + 40 < v18 )
    return 3221225621LL;
  v20 = (struct _PAC_INFO_BUFFER *)MIDL_user_allocate(v19);
  *a6 = v20;
  if ( !v20 )
    return 3221225495LL;
  *(_DWORD *)v20 = 12;
  *((_DWORD *)*a6 + 1) = v19 - 16;
  v22 = (char *)*a6 + 16;
  *((_QWORD *)*a6 + 1) = v22;
  *((_DWORD *)v22 + 2) = 2;
  if ( a1 )
    *((_DWORD *)v22 + 2) = 3;
  *(_WORD *)v22 = a2->Length;
  *((_WORD *)v22 + 1) = 24;
  memcpy_0(v22 + 24, a2->Buffer, a2->Length);
  v23 = &v22[((a2->Length + 7LL) & 0xFFFFFFFFFFFFFFF8uLL) + 24];
  if ( (__int64)(((a2->Length + 7LL) & 0xFFFFFFFFFFFFFFF8uLL) + 24) > 0xFFFF )
    return 3221225621LL;
  *((_WORD *)v22 + 2) = a3->Length;
  *((_WORD *)v22 + 3) = (_WORD)v23 - (_WORD)v22;
  memcpy_0(v23, a3->Buffer, a3->Length);
  v24 = &v23[(a3->Length + 7LL) & 0xFFFFFFFFFFFFFFF8uLL];
  if ( v24 - v22 > 0xFFFF )
    return 3221225621LL;
  *((_WORD *)v22 + 6) = a4->Length;
  *((_WORD *)v22 + 7) = (_WORD)v24 - (_WORD)v22;
  memcpy_0(v24, a4->Buffer, a4->Length);
  v25 = &v24[(a4->Length + 7LL) & 0xFFFFFFFFFFFFFFF8uLL];
  if ( v25 - v22 > 0xFFFF )
    return 3221225621LL;
  v26 = RtlLengthSid(Sid);
  *((_WORD *)v22 + 8) = v26;
  *((_WORD *)v22 + 9) = (_WORD)v25 - (_WORD)v22;
  memcpy_0(v25, Sid, v26);
  return 0;
}

```

## disassembly

```asm
0x18005d344  push    rbx
0x18005d346  push    rbp
0x18005d347  push    rsi
0x18005d348  push    rdi
0x18005d349  push    r12
0x18005d34b  push    r14
0x18005d34d  push    r15
0x18005d34f  sub     rsp, 80h
0x18005d356  mov     rax, cs:__security_cookie
0x18005d35d  xor     rax, rsp
0x18005d360  mov     [rsp+0B8h+var_48], rax
0x18005d365  mov     rdi, [rsp+0B8h+arg_28]
0x18005d36d  mov     r15, rdx
0x18005d370  xor     edx, edx; Val
0x18005d372  mov     r14, r8
0x18005d375  mov     bpl, cl
0x18005d378  mov     rsi, r9
0x18005d37b  lea     rcx, [rsp+0B8h+Sid]; void *
0x18005d380  lea     r8d, [rdx+48h]; Size
0x18005d384  call    memset_0
0x18005d389  mov     edx, [rsp+0B8h+arg_20]; unsigned int
0x18005d390  lea     rcx, [rsp+0B8h+Sid]; Sid
0x18005d395  call    ?KdcMakeAccountSid@@YAXPEAXK@Z; KdcMakeAccountSid(void *,ulong)
0x18005d39a  movzx   eax, word ptr [r15]
0x18005d39e  mov     r12d, 0FFFFFFF8h
0x18005d3a4  lea     r8d, [rax+7]
0x18005d3a8  and     r8d, r12d
0x18005d3ab  cmp     eax, r8d
0x18005d3ae  ja      loc_18005D547
0x18005d3b4  movzx   eax, word ptr [r14]
0x18005d3b8  lea     ecx, [rax+7]
0x18005d3bb  and     ecx, r12d
0x18005d3be  cmp     eax, ecx
0x18005d3c0  ja      loc_18005D547
0x18005d3c6  movzx   eax, word ptr [rsi]
0x18005d3c9  lea     edx, [rax+7]
0x18005d3cc  and     edx, r12d
0x18005d3cf  cmp     eax, edx
0x18005d3d1  ja      loc_18005D547
0x18005d3d7  lea     eax, [rcx+r8]
0x18005d3db  cmp     eax, r8d
0x18005d3de  jb      loc_18005D547
0x18005d3e4  lea     ebx, [rax+rdx]
0x18005d3e7  cmp     ebx, eax
0x18005d3e9  jb      loc_18005D547
0x18005d3ef  lea     rcx, [rsp+0B8h+Sid]; Sid
0x18005d3f4  call    cs:__imp_RtlLengthSid
0x18005d3fa  lea     ecx, [rax+7]
0x18005d3fd  and     ecx, r12d
0x18005d400  add     ecx, ebx
0x18005d402  cmp     ecx, ebx
0x18005d404  jb      loc_18005D547
0x18005d40a  lea     ebx, [rcx+28h]
0x18005d40d  cmp     ebx, ecx
0x18005d40f  jb      loc_18005D547
0x18005d415  mov     ecx, ebx; size
0x18005d417  call    MIDL_user_allocate
0x18005d41c  mov     [rdi], rax
0x18005d41f  test    rax, rax
0x18005d422  jnz     short loc_18005D42E
0x18005d424  mov     eax, 0C0000017h
0x18005d429  jmp     loc_18005D54C
0x18005d42e  mov     dword ptr [rax], 0Ch
0x18005d434  lea     ecx, [rbx-10h]
0x18005d437  mov     rax, [rdi]
0x18005d43a  mov     [rax+4], ecx
0x18005d43d  mov     rax, [rdi]
0x18005d440  lea     rdi, [rax+10h]
0x18005d444  mov     [rax+8], rdi
0x18005d448  mov     dword ptr [rdi+8], 2
0x18005d44f  test    bpl, bpl
0x18005d452  jz      short loc_18005D45B
0x18005d454  mov     dword ptr [rdi+8], 3
0x18005d45b  movzx   eax, word ptr [r15]
0x18005d45f  lea     rbx, [rdi+18h]
0x18005d463  mov     [rdi], ax
0x18005d466  mov     rcx, rbx; void *
0x18005d469  movzx   eax, bx
0x18005d46c  sub     ax, di
0x18005d46f  mov     [rdi+2], ax
0x18005d473  movzx   r8d, word ptr [r15]; Size
0x18005d477  mov     rdx, [r15+8]; Src
0x18005d47b  call    memcpy_0
0x18005d480  movzx   eax, word ptr [r15]
0x18005d484  mov     ebp, 0FFFFh
0x18005d489  add     rax, 7
0x18005d48d  and     rax, 0FFFFFFFFFFFFFFF8h
0x18005d491  add     rbx, rax
0x18005d494  mov     rax, rbx
0x18005d497  sub     rax, rdi
0x18005d49a  cmp     rax, rbp
0x18005d49d  jg      loc_18005D547
0x18005d4a3  movzx   eax, word ptr [r14]
0x18005d4a7  mov     rcx, rbx; void *
0x18005d4aa  mov     [rdi+4], ax
0x18005d4ae  movzx   eax, bx
0x18005d4b1  sub     ax, di
0x18005d4b4  mov     [rdi+6], ax
0x18005d4b8  movzx   r8d, word ptr [r14]; Size
0x18005d4bc  mov     rdx, [r14+8]; Src
0x18005d4c0  call    memcpy_0
0x18005d4c5  movzx   eax, word ptr [r14]
0x18005d4c9  add     rax, 7
0x18005d4cd  and     rax, 0FFFFFFFFFFFFFFF8h
0x18005d4d1  add     rbx, rax
0x18005d4d4  mov     rax, rbx
0x18005d4d7  sub     rax, rdi
0x18005d4da  cmp     rax, rbp
0x18005d4dd  jg      short loc_18005D547
0x18005d4df  movzx   eax, word ptr [rsi]
0x18005d4e2  mov     rcx, rbx; void *
0x18005d4e5  mov     [rdi+0Ch], ax
0x18005d4e9  movzx   eax, bx
0x18005d4ec  sub     ax, di
0x18005d4ef  mov     [rdi+0Eh], ax
0x18005d4f3  movzx   r8d, word ptr [rsi]; Size
0x18005d4f7  mov     rdx, [rsi+8]; Src
0x18005d4fb  call    memcpy_0
0x18005d500  movzx   eax, word ptr [rsi]
0x18005d503  add     rax, 7
0x18005d507  and     rax, 0FFFFFFFFFFFFFFF8h
0x18005d50b  add     rbx, rax
0x18005d50e  mov     rax, rbx
0x18005d511  sub     rax, rdi
0x18005d514  cmp     rax, rbp
0x18005d517  jg      short loc_18005D547
0x18005d519  lea     rcx, [rsp+0B8h+Sid]; Sid
0x18005d51e  call    cs:__imp_RtlLengthSid
0x18005d524  movzx   edx, bx
0x18005d527  movzx   r8d, ax; Size
0x18005d52b  mov     rcx, rbx; void *
0x18005d52e  mov     [rdi+10h], ax
0x18005d532  sub     dx, di
0x18005d535  mov     [rdi+12h], dx
0x18005d539  lea     rdx, [rsp+0B8h+Sid]; Src
0x18005d53e  call    memcpy_0
0x18005d543  xor     eax, eax
0x18005d545  jmp     short loc_18005D54C
0x18005d547  mov     eax, 0C0000095h
0x18005d54c  mov     rcx, [rsp+0B8h+var_48]
0x18005d551  xor     rcx, rsp; StackCookie
0x18005d554  call    __security_check_cookie
0x18005d559  add     rsp, 80h
0x18005d560  pop     r15
0x18005d562  pop     r14
0x18005d564  pop     r12
0x18005d566  pop     rdi
0x18005d567  pop     rsi
0x18005d568  pop     rbp
0x18005d569  pop     rbx
0x18005d56a  retn
```
