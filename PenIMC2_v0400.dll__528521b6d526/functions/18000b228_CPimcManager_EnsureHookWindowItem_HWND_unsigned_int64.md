# CPimcManager::EnsureHookWindowItem(HWND__ *,unsigned __int64 *)

- ea: `0x18000b228`
- end: `0x18000b354`
- name: `?EnsureHookWindowItem@CPimcManager@@QEAAJPEAUHWND__@@PEA_K@Z`
- size: `300`
- prototype: `int(CPimcManager *__hidden this, HWND, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x18000ada8`

## callees

- `0x18000b228`
- `0x18000d44c`

## import_xrefs

- `USER32!GetParent` at `0x18000b322`
- `USER32!GetParent` at `0x18000b322`
- `USER32!GetWindowThreadProcessId` at `0x18000b2ee`
- `USER32!GetWindowThreadProcessId` at `0x18000b308`
- `USER32!GetWindowThreadProcessId` at `0x18000b2ee`
- `USER32!GetWindowThreadProcessId` at `0x18000b308`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CPimcManager::EnsureHookWindowItem(CPimcManager *this, HWND a2, unsigned __int64 *a3)
{
  unsigned int v6; // ebx
  unsigned __int64 v7; // rcx
  unsigned __int64 v8; // rax
  _DWORD *v9; // rcx
  __int64 v10; // rax
  DWORD WindowThreadProcessId; // r14d
  HWND i; // rcx
  DWORD v13; // ecx
  HWND Parent; // rax
  HWND v15; // rdi
  DWORD dwProcessId; // [rsp+50h] [rbp+8h] BYREF
  _DWORD *v18; // [rsp+60h] [rbp+18h] BYREF
  _DWORD *v19; // [rsp+68h] [rbp+20h]

  v6 = 0;
  v7 = 0;
  v8 = *((_QWORD *)this + 2);
  if ( v8 )
  {
    while ( *(HWND *)v8 != a2 )
    {
      v8 = *(_QWORD *)(v8 + 72);
      if ( !v8 )
      {
        *a3 = 0;
        goto LABEL_7;
      }
    }
    v7 = v8;
  }
  *a3 = v7;
  if ( !v7 )
  {
LABEL_7:
    v9 = operator new(0x50u);
    v18 = v9;
    v19 = v9;
    v9[15] = 0;
    v9[14] = 2;
    *((_QWORD *)v9 + 6) = v9 + 8;
    v6 = v9 == 0 ? 0x8007000E : 0;
    if ( v9 )
    {
      if ( !*((_QWORD *)this + 2) )
        *((_QWORD *)this + 2) = v9;
      *((_QWORD *)v9 + 8) = *((_QWORD *)this + 3);
      *((_QWORD *)v9 + 9) = 0;
      v10 = *((_QWORD *)this + 3);
      if ( v10 )
        *(_QWORD *)(v10 + 72) = v9;
      *((_QWORD *)this + 3) = v9;
      *a3 = (unsigned __int64)v9;
      v6 = 0;
      *(_QWORD *)v9 = a2;
      *(_DWORD *)(*a3 + 8) = 0;
      dwProcessId = 0;
      WindowThreadProcessId = GetWindowThreadProcessId(a2, &dwProcessId);
      for ( i = a2; ; i = v15 )
      {
        Parent = GetParent(i);
        v15 = Parent;
        if ( !Parent )
          break;
        LODWORD(v18) = 0;
        v13 = GetWindowThreadProcessId(Parent, (LPDWORD)&v18);
        if ( (_DWORD)v18 != dwProcessId || v13 != WindowThreadProcessId )
        {
          *(_OWORD *)(*a3 + 12) = 0;
          *(_DWORD *)(*a3 + 8) = 1;
          return v6;
        }
      }
    }
  }
  return v6;
}

```

## disassembly

```asm
0x18000b228  push    rbx
0x18000b22a  push    rbp
0x18000b22b  push    rsi
0x18000b22c  push    rdi
0x18000b22d  push    r14
0x18000b22f  sub     rsp, 20h
0x18000b233  mov     rsi, r8
0x18000b236  mov     rbp, rdx
0x18000b239  mov     rdi, rcx
0x18000b23c  xor     ebx, ebx
0x18000b23e  xor     ecx, ecx
0x18000b240  mov     rax, [rdi+10h]
0x18000b244  test    rax, rax
0x18000b247  jz      short loc_18000B25F
0x18000b249  cmp     [rax], rbp
0x18000b24c  jz      short loc_18000B25C
0x18000b24e  mov     rax, [rax+48h]
0x18000b252  test    rax, rax
0x18000b255  jnz     short loc_18000B249
0x18000b257  and     [r8], rcx
0x18000b25a  jmp     short loc_18000B26B
0x18000b25c  mov     rcx, rax
0x18000b25f  mov     [r8], rcx
0x18000b262  test    rcx, rcx
0x18000b265  jnz     loc_18000B347
0x18000b26b  mov     ecx, 50h ; 'P'; Size
0x18000b270  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000b275  mov     rcx, rax
0x18000b278  mov     [rsp+48h+arg_10], rax
0x18000b27d  mov     [rsp+48h+arg_18], rax
0x18000b282  add     rax, 20h ; ' '
0x18000b286  and     dword ptr [rax+1Ch], 0
0x18000b28a  mov     dword ptr [rax+18h], 2
0x18000b291  mov     [rax+10h], rax
0x18000b295  mov     rax, rcx
0x18000b298  neg     rax
0x18000b29b  sbb     ebx, ebx
0x18000b29d  not     ebx
0x18000b29f  and     ebx, 8007000Eh
0x18000b2a5  jl      loc_18000B347
0x18000b2ab  cmp     qword ptr [rdi+10h], 0
0x18000b2b0  jnz     short loc_18000B2B6
0x18000b2b2  mov     [rdi+10h], rcx
0x18000b2b6  mov     rax, [rdi+18h]
0x18000b2ba  mov     [rcx+40h], rax
0x18000b2be  and     qword ptr [rcx+48h], 0
0x18000b2c3  mov     rax, [rdi+18h]
0x18000b2c7  test    rax, rax
0x18000b2ca  jz      short loc_18000B2D0
0x18000b2cc  mov     [rax+48h], rcx
0x18000b2d0  mov     [rdi+18h], rcx
0x18000b2d4  mov     [rsi], rcx
0x18000b2d7  xor     ebx, ebx
0x18000b2d9  mov     [rcx], rbp
0x18000b2dc  mov     rax, [rsi]
0x18000b2df  and     [rax+8], ebx
0x18000b2e2  and     [rsp+48h+dwProcessId], ebx
0x18000b2e6  lea     rdx, [rsp+48h+dwProcessId]; lpdwProcessId
0x18000b2eb  mov     rcx, rbp; hWnd
0x18000b2ee  call    cs:__imp_GetWindowThreadProcessId
0x18000b2f4  mov     r14d, eax
0x18000b2f7  mov     rcx, rbp
0x18000b2fa  jmp     short loc_18000B322
0x18000b2fc  and     dword ptr [rsp+48h+arg_10], ebx
0x18000b300  lea     rdx, [rsp+48h+arg_10]; lpdwProcessId
0x18000b305  mov     rcx, rdi; hWnd
0x18000b308  call    cs:__imp_GetWindowThreadProcessId
0x18000b30e  mov     ecx, eax
0x18000b310  mov     eax, [rsp+48h+dwProcessId]
0x18000b314  cmp     dword ptr [rsp+48h+arg_10], eax
0x18000b318  jnz     short loc_18000B332
0x18000b31a  cmp     ecx, r14d
0x18000b31d  jnz     short loc_18000B332
0x18000b31f  mov     rcx, rdi; hWnd
0x18000b322  call    cs:__imp_GetParent
0x18000b328  test    rax, rax
0x18000b32b  mov     rdi, rax
0x18000b32e  jnz     short loc_18000B2FC
0x18000b330  jmp     short loc_18000B347
0x18000b332  xorps   xmm0, xmm0
0x18000b335  mov     rax, [rsi]
0x18000b338  movdqu  xmmword ptr [rax+0Ch], xmm0
0x18000b33d  mov     rax, [rsi]
0x18000b340  mov     dword ptr [rax+8], 1
0x18000b347  mov     eax, ebx
0x18000b349  add     rsp, 20h
0x18000b34d  pop     r14
0x18000b34f  pop     rdi
0x18000b350  pop     rsi
0x18000b351  pop     rbp
0x18000b352  pop     rbx
0x18000b353  retn
```
