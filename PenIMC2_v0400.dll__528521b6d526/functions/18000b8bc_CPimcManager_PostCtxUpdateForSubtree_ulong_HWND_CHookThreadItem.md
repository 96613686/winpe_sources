# CPimcManager::PostCtxUpdateForSubtree(ulong,HWND__ *,CHookThreadItem *)

- ea: `0x18000b8bc`
- end: `0x18000bb1f`
- name: `?PostCtxUpdateForSubtree@CPimcManager@@SAXKPEAUHWND__@@PEAUCHookThreadItem@@@Z`
- size: `611`
- prototype: `void __fastcall(unsigned int, HWND, struct CHookThreadItem *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, installer_update`

## callers

- `0x18000b834`

## callees

- `0x180006f08`
- `0x18000b8bc`
- `0x18000cdb0`
- `0x18000ce0c`
- `0x18000d44c`

## import_xrefs

- `USER32!GetWindow` at `0x18000ba39`
- `USER32!GetWindow` at `0x18000ba4e`
- `USER32!GetWindow` at `0x18000babb`
- `USER32!GetWindow` at `0x18000ba39`
- `USER32!GetWindow` at `0x18000ba4e`
- `USER32!GetWindow` at `0x18000babb`
- `USER32!GetWindowRect` at `0x18000b9d9`
- `USER32!GetWindowRect` at `0x18000b9d9`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CPimcManager::PostCtxUpdateForSubtree(unsigned int a1, HWND a2, struct CHookThreadItem *a3)
{
  struct CHookThreadItem *v3; // r12
  char v5; // r14
  unsigned int v6; // r15d
  HWND *v7; // rbx
  HWND *v8; // rsi
  HWND v9; // r13
  HWND *v10; // rcx
  HWND v11; // rax
  int v12; // eax
  __int64 i; // rdi
  int v14; // r12d
  __int64 j; // r14
  HWND Window; // rax
  HWND k; // rdi
  HWND *v18; // rax
  HWND *v19; // rcx
  int v21; // [rsp+48h] [rbp-60h]
  struct tagRECT Rect; // [rsp+60h] [rbp-48h] BYREF

  v3 = a3;
  v5 = a1;
  try
  {
    v6 = 0;
    v7 = (HWND *)operator new(0x18u);
    if ( v7 )
    {
      v7[1] = 0;
      v7[2] = 0;
      v8 = v7;
      *v7 = a2;
      while ( v7 )
      {
        v9 = *v7;
        v10 = v7;
        v11 = v7[1];
        v7 = (HWND *)v7[2];
        if ( v11 )
          *((_QWORD *)v11 + 2) = v7;
        if ( v7 )
          v7[1] = v11;
        if ( v8 == v10 )
          v8 = (HWND *)v11;
        operator delete(v10);
        v12 = *((_DWORD *)v3 + 13);
        v21 = v12;
        while ( (int)v6 < v12 )
        {
          for ( i = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)v3 + 5) + 8LL * v6) + 16LL); i; i = *(_QWORD *)(i + 72) )
          {
            if ( *(HWND *)i == v9 )
            {
              if ( *(_DWORD *)(i + 8) && (v5 & 1) != 0 )
              {
                Rect = 0;
                GetWindowRect(*(HWND *)i, &Rect);
                *(struct tagRECT *)(i + 12) = Rect;
              }
              v14 = *(_DWORD *)(i + 60);
              for ( j = 0; (int)j < v14; j = (unsigned int)(j + 1) )
                CPimcContext::PostUpdate(*(CPimcContext **)(*(_QWORD *)(i + 48) + 8 * j), a1);
              v5 = a1;
              v3 = a3;
              break;
            }
          }
          ++v6;
          v12 = v21;
        }
        Window = GetWindow(v9, 5u);
        v6 = 0;
        if ( Window )
        {
          for ( k = GetWindow(Window, 1u); k; k = GetWindow(k, 3u) )
          {
            v18 = (HWND *)operator new(0x18u);
            if ( !v18 )
              goto LABEL_35;
            if ( !v7 )
              v7 = v18;
            v18[1] = (HWND)v8;
            v18[2] = 0;
            if ( v8 )
              v8[2] = (HWND)v18;
            v8 = v18;
            *v18 = k;
          }
        }
      }
    }
    else
    {
      v7 = 0;
    }
LABEL_35:
    while ( v7 )
    {
      v19 = v7;
      v7 = (HWND *)v7[2];
      operator delete(v19);
    }
  }
  catch ( ... )
  {
  }
}

```

## disassembly

```asm
0x18000b8bc  mov     [rsp+arg_0], rbx
0x18000b8c1  mov     [rsp+arg_8], rsi
0x18000b8c6  push    rdi
0x18000b8c7  push    r12
0x18000b8c9  push    r13
0x18000b8cb  push    r14
0x18000b8cd  push    r15
0x18000b8cf  sub     rsp, 80h
0x18000b8d6  mov     rax, cs:__security_cookie
0x18000b8dd  xor     rax, rsp
0x18000b8e0  mov     [rsp+0A8h+var_38], rax
0x18000b8e5  mov     r12, r8
0x18000b8e8  mov     [rsp+0A8h+var_58], r8
0x18000b8ed  mov     rdi, rdx
0x18000b8f0  mov     r14d, ecx
0x18000b8f3  mov     [rsp+0A8h+var_84], ecx
0x18000b8f7  xorps   xmm0, xmm0
0x18000b8fa  movdqu  [rsp+0A8h+var_78], xmm0
0x18000b900  xor     r15d, r15d
0x18000b903  mov     [rsp+0A8h+var_88], r15d
0x18000b908  lea     ecx, [r15+18h]; Size
0x18000b90c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000b911  mov     rbx, rax
0x18000b914  neg     rax
0x18000b917  sbb     ecx, ecx
0x18000b919  not     ecx
0x18000b91b  and     ecx, 8007000Eh
0x18000b921  mov     [rsp+0A8h+var_88], ecx
0x18000b925  jl      loc_18000BACB
0x18000b92b  mov     qword ptr [rsp+0A8h+var_78], rbx
0x18000b930  mov     [rbx+8], r15
0x18000b934  mov     [rbx+10h], r15
0x18000b938  mov     rsi, rbx
0x18000b93b  mov     qword ptr [rsp+0A8h+var_78+8], rbx
0x18000b940  mov     [rsp+0A8h+var_88], r15d
0x18000b945  mov     [rbx], rdi
0x18000b948  test    rbx, rbx
0x18000b94b  jz      loc_18000BAD0
0x18000b951  mov     r13, [rbx]
0x18000b954  mov     rcx, rbx; Block
0x18000b957  mov     rax, [rbx+8]
0x18000b95b  mov     rbx, [rbx+10h]
0x18000b95f  test    rax, rax
0x18000b962  jz      short loc_18000B968
0x18000b964  mov     [rax+10h], rbx
0x18000b968  test    rbx, rbx
0x18000b96b  jz      short loc_18000B971
0x18000b96d  mov     [rbx+8], rax
0x18000b971  mov     qword ptr [rsp+0A8h+var_78], rbx
0x18000b976  cmp     rsi, rcx
0x18000b979  cmovz   rsi, rax
0x18000b97d  mov     qword ptr [rsp+0A8h+var_78+8], rsi
0x18000b982  mov     edx, 18h
0x18000b987  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000b98c  mov     eax, [r12+34h]
0x18000b991  mov     [rsp+0A8h+var_60], eax
0x18000b995  mov     [rsp+0A8h+var_64], r15d
0x18000b99a  cmp     r15d, eax
0x18000b99d  jge     loc_18000BA31
0x18000b9a3  mov     ecx, r15d
0x18000b9a6  mov     rax, [r12+28h]
0x18000b9ab  mov     rcx, [rax+rcx*8]
0x18000b9af  mov     rdi, [rcx+10h]
0x18000b9b3  test    rdi, rdi
0x18000b9b6  jz      short loc_18000BA20
0x18000b9b8  cmp     [rdi], r13
0x18000b9bb  jnz     short loc_18000BA10
0x18000b9bd  cmp     dword ptr [rdi+8], 0
0x18000b9c1  jz      short loc_18000B9E9
0x18000b9c3  test    r14b, 1
0x18000b9c7  jz      short loc_18000B9E9
0x18000b9c9  xorps   xmm0, xmm0
0x18000b9cc  movups  xmmword ptr [rsp+0A8h+Rect.left], xmm0
0x18000b9d1  lea     rdx, [rsp+0A8h+Rect]; lpRect
0x18000b9d6  mov     rcx, [rdi]; hWnd
0x18000b9d9  call    cs:__imp_GetWindowRect
0x18000b9df  movups  xmm0, xmmword ptr [rsp+0A8h+Rect.left]
0x18000b9e4  movdqu  xmmword ptr [rdi+0Ch], xmm0
0x18000b9e9  mov     r12d, [rdi+3Ch]
0x18000b9ed  xor     r14d, r14d
0x18000b9f0  mov     [rsp+0A8h+var_68], r14d
0x18000b9f5  cmp     r14d, r12d
0x18000b9f8  jge     short loc_18000BA16
0x18000b9fa  mov     rax, [rdi+30h]
0x18000b9fe  mov     edx, [rsp+0A8h+var_84]; unsigned int
0x18000ba02  mov     rcx, [rax+r14*8]; this
0x18000ba06  call    ?PostUpdate@CPimcContext@@QEAAJK@Z; CPimcContext::PostUpdate(ulong)
0x18000ba0b  inc     r14d
0x18000ba0e  jmp     short loc_18000B9F0
0x18000ba10  mov     rdi, [rdi+48h]
0x18000ba14  jmp     short loc_18000B9B3
0x18000ba16  mov     r14d, [rsp+0A8h+var_84]
0x18000ba1b  mov     r12, [rsp+0A8h+var_58]
0x18000ba20  inc     r15d
0x18000ba23  mov     [rsp+0A8h+var_64], r15d
0x18000ba28  mov     eax, [rsp+0A8h+var_60]
0x18000ba2c  jmp     loc_18000B99A
0x18000ba31  mov     edx, 5; uCmd
0x18000ba36  mov     rcx, r13; hWnd
0x18000ba39  call    cs:__imp_GetWindow
0x18000ba3f  xor     r15d, r15d
0x18000ba42  test    rax, rax
0x18000ba45  jz      short loc_18000BAC6
0x18000ba47  lea     edx, [r15+1]; uCmd
0x18000ba4b  mov     rcx, rax; hWnd
0x18000ba4e  call    cs:__imp_GetWindow
0x18000ba54  mov     rdi, rax
0x18000ba57  test    rdi, rdi
0x18000ba5a  jz      short loc_18000BAC6
0x18000ba5c  mov     [rsp+0A8h+var_80], r15d
0x18000ba61  mov     ecx, 18h; Size
0x18000ba66  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000ba6b  mov     rcx, rax
0x18000ba6e  neg     rcx
0x18000ba71  sbb     edx, edx
0x18000ba73  not     edx
0x18000ba75  and     edx, 8007000Eh
0x18000ba7b  mov     [rsp+0A8h+var_80], edx
0x18000ba7f  jl      short loc_18000BAD0
0x18000ba81  test    rbx, rbx
0x18000ba84  cmovz   rbx, rax
0x18000ba88  mov     qword ptr [rsp+0A8h+var_78], rbx
0x18000ba8d  mov     [rax+8], rsi
0x18000ba91  mov     [rax+10h], r15
0x18000ba95  test    rsi, rsi
0x18000ba98  jz      short loc_18000BA9E
0x18000ba9a  mov     [rsi+10h], rax
0x18000ba9e  mov     rsi, rax
0x18000baa1  mov     qword ptr [rsp+0A8h+var_78+8], rax
0x18000baa6  mov     [rsp+0A8h+var_80], r15d
0x18000baab  mov     [rsp+0A8h+var_50], rax
0x18000bab0  mov     [rax], rdi
0x18000bab3  mov     edx, 3; uCmd
0x18000bab8  mov     rcx, rdi; hWnd
0x18000babb  call    cs:__imp_GetWindow
0x18000bac1  mov     rdi, rax
0x18000bac4  jmp     short loc_18000BA57
0x18000bac6  jmp     loc_18000B948
0x18000bacb  mov     rbx, qword ptr [rsp+0A8h+var_78]
0x18000bad0  test    rbx, rbx
0x18000bad3  jz      short loc_18000BAE8
0x18000bad5  mov     rcx, rbx; Block
0x18000bad8  mov     rbx, [rbx+10h]
0x18000badc  mov     edx, 18h
0x18000bae1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000bae6  jmp     short loc_18000BAD0
0x18000bae8  mov     qword ptr [rsp+0A8h+var_78+8], r15
0x18000baed  mov     qword ptr [rsp+0A8h+var_78], r15
0x18000baf2  jmp     short $+2
0x18000baf4  mov     rcx, [rsp+0A8h+var_38]
0x18000baf9  xor     rcx, rsp; StackCookie
0x18000bafc  call    __security_check_cookie
0x18000bb01  lea     r11, [rsp+0A8h+var_28]
0x18000bb09  mov     rbx, [r11+30h]
0x18000bb0d  mov     rsi, [r11+38h]
0x18000bb11  mov     rsp, r11
0x18000bb14  pop     r15
0x18000bb16  pop     r14
0x18000bb18  pop     r13
0x18000bb1a  pop     r12
0x18000bb1c  pop     rdi
0x18000bb1d  retn
```
