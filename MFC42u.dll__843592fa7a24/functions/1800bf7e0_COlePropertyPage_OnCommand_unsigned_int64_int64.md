# COlePropertyPage::OnCommand(unsigned __int64,__int64)

- ea: `0x1800bf7e0`
- end: `0x1800bfa5d`
- name: `?OnCommand@COlePropertyPage@@MEAAH_K_J@Z`
- size: `637`
- prototype: `__int64 __fastcall(COlePropertyPage *__hidden this, unsigned __int64, __int64)`
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18000fb70`
- `0x18003aff0`
- `0x1800be710`
- `0x1800bf7e0`
- `0x1800bfd70`
- `0x1800d1fe0`
- `0x1800d7010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800bf8de`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800bf922`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800bf9d9`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800bf8de`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800bf922`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800bf9d9`
- `USER32!GetWindowLongW` at `0x1800bf935`
- `USER32!GetWindowLongW` at `0x1800bf94d`
- `USER32!GetWindowLongW` at `0x1800bf976`
- `USER32!GetWindowLongW` at `0x1800bf935`
- `USER32!GetWindowLongW` at `0x1800bf94d`
- `USER32!GetWindowLongW` at `0x1800bf976`
- `USER32!GetWindow` at `0x1800bf961`
- `USER32!GetWindow` at `0x1800bf961`
- `USER32!GetClassNameW` at `0x1800bf89b`
- `USER32!GetClassNameW` at `0x1800bf89b`

## pseudocode

```c
__int64 __fastcall COlePropertyPage::OnCommand(COlePropertyPage *this, unsigned __int64 a2, __int64 a3)
{
  HWND Window; // rdi
  unsigned int v6; // r13d
  int v7; // esi
  LONG WindowLongW; // r12d
  int v9; // ebp
  unsigned int v10; // esi
  unsigned __int64 v11; // r14
  unsigned int i; // ebp
  int v13; // eax
  unsigned int j; // edi
  WCHAR ClassName[104]; // [rsp+40h] [rbp-118h] BYREF

  Window = (HWND)a3;
  v6 = CWnd::OnCommand(this, a2, a3);
  if ( !*((_DWORD *)this + 80) && *((_QWORD *)this + 37) && Window )
  {
    v7 = 0;
    WindowLongW = (unsigned __int16)a2;
    v9 = 0;
    if ( *((__int64 *)this + 44) <= 0 )
      goto LABEL_9;
    do
    {
      if ( (unsigned __int16)a2 == CUIntArray::GetAt((COlePropertyPage *)((char *)this + 336), v9) )
        v7 = 1;
      ++v9;
    }
    while ( v9 < *((_QWORD *)this + 44) );
    if ( !v7 )
    {
LABEL_9:
      v10 = 0;
      v11 = a2 >> 16;
      GetClassNameW(Window, ClassName, 100);
      for ( i = 0; i < 6; ++i )
      {
        if ( CompareStringW(0x7Fu, 1u, *((PCNZWCH *)&_afxNotifyList + 2 * (int)i), -1, ClassName, -1) == 2
          && word_1800F0B08[8 * i] == (_WORD)v11 )
        {
          if ( CompareStringW(0x7Fu, 1u, ClassName, -1, L"button", -1) == 2 )
          {
            v13 = GetWindowLongW(Window, -16) & 0xF;
            if ( v13 == 4 || v13 == 9 )
            {
              while ( (GetWindowLongW(Window, -16) & 0x20000) == 0 )
              {
                Window = GetWindow(Window, 3u);
                if ( !Window )
                  goto LABEL_21;
              }
              WindowLongW = GetWindowLongW(Window, -12);
            }
          }
LABEL_21:
          *((_DWORD *)this + 58) = 1;
          COlePropertyPage::SetControlStatus(this, WindowLongW, 1);
          v10 = 1;
          break;
        }
      }
      if ( *((_DWORD *)this + 58) )
      {
        for ( j = 0; j < 6; ++j )
        {
          if ( CompareStringW(0x7Fu, 1u, *((PCNZWCH *)&_afxUpdateList + 2 * (int)j), -1, ClassName, -1) == 2
            && word_1800F0AA8[8 * j] == (_WORD)v11
            && (unsigned int)COlePropertyPage::GetControlStatus(this, WindowLongW) )
          {
            v10 |= 2u;
          }
        }
      }
      if ( v10 )
        (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 36) + 24LL))(*((_QWORD *)this + 36), v10);
    }
  }
  return v6;
}

```

## disassembly

```asm
0x1800bf7e0  mov     [rsp+arg_18], rbx
0x1800bf7e5  push    rbp
0x1800bf7e6  push    rsi
0x1800bf7e7  push    rdi
0x1800bf7e8  push    r12
0x1800bf7ea  push    r13
0x1800bf7ec  push    r14
0x1800bf7ee  push    r15
0x1800bf7f0  sub     rsp, 120h
0x1800bf7f7  mov     rax, cs:__security_cookie
0x1800bf7fe  xor     rax, rsp
0x1800bf801  mov     [rsp+158h+var_48], rax
0x1800bf809  mov     rdi, r8
0x1800bf80c  mov     r14, rdx
0x1800bf80f  mov     rbx, rcx
0x1800bf812  call    ?OnCommand@CWnd@@MEAAH_K_J@Z; CWnd::OnCommand(unsigned __int64,__int64)
0x1800bf817  cmp     dword ptr [rbx+140h], 0
0x1800bf81e  mov     r13d, eax
0x1800bf821  mov     [rsp+158h+var_128], eax
0x1800bf825  jnz     loc_1800BFA2F
0x1800bf82b  cmp     qword ptr [rbx+128h], 0
0x1800bf833  jz      loc_1800BFA2F
0x1800bf839  test    rdi, rdi
0x1800bf83c  jz      loc_1800BFA2F
0x1800bf842  xor     esi, esi
0x1800bf844  movzx   r12d, r14w
0x1800bf848  xor     ebp, ebp
0x1800bf84a  cmp     [rbx+160h], rsi
0x1800bf851  jle     short loc_1800BF889
0x1800bf853  lea     r13d, [rsi+1]
0x1800bf857  movsxd  rdx, ebp; __int64
0x1800bf85a  lea     rcx, [rbx+150h]; this
0x1800bf861  call    ?GetAt@CUIntArray@@QEBAI_J@Z; CUIntArray::GetAt(__int64)
0x1800bf866  cmp     r12d, eax
0x1800bf869  cmovz   esi, r13d
0x1800bf86d  add     ebp, r13d
0x1800bf870  movsxd  rax, ebp
0x1800bf873  cmp     rax, [rbx+160h]
0x1800bf87a  jl      short loc_1800BF857
0x1800bf87c  mov     r13d, [rsp+158h+var_128]
0x1800bf881  test    esi, esi
0x1800bf883  jnz     loc_1800BFA2F
0x1800bf889  xor     esi, esi
0x1800bf88b  shr     r14, 10h
0x1800bf88f  lea     rdx, [rsp+158h+ClassName]; lpClassName
0x1800bf894  mov     rcx, rdi; hWnd
0x1800bf897  lea     r8d, [rsi+64h]; nMaxCount
0x1800bf89b  call    cs:__imp_GetClassNameW
0x1800bf8a1  xor     ebp, ebp
0x1800bf8a3  lea     rcx, __ImageBase
0x1800bf8aa  cmp     ebp, 6
0x1800bf8ad  jnb     loc_1800BF99E
0x1800bf8b3  or      r9d, 0FFFFFFFFh; cchCount1
0x1800bf8b7  movsxd  r15, ebp
0x1800bf8ba  lea     rax, [rsp+158h+ClassName]
0x1800bf8bf  mov     [rsp+158h+cchCount2], 0FFFFFFFFh; cchCount2
0x1800bf8c7  add     r15, r15
0x1800bf8ca  mov     [rsp+158h+lpString2], rax; lpString2
0x1800bf8cf  lea     edx, [r9+2]; dwCmpFlags
0x1800bf8d3  mov     r8, ds:rva ?_afxNotifyList@@3QBUNotifyInfo@@B[rcx+r15*8]; lpString1
0x1800bf8db  lea     ecx, [rdx+7Eh]; Locale
0x1800bf8de  call    cs:__imp_CompareStringW
0x1800bf8e4  lea     rcx, __ImageBase
0x1800bf8eb  cmp     eax, 2
0x1800bf8ee  jnz     short loc_1800BF8FB
0x1800bf8f0  cmp     ds:rva word_1800F0B08[rcx+r15*8], r14w
0x1800bf8f9  jz      short loc_1800BF8FF
0x1800bf8fb  inc     ebp
0x1800bf8fd  jmp     short loc_1800BF8AA
0x1800bf8ff  or      r9d, 0FFFFFFFFh; cchCount1
0x1800bf903  lea     rax, aButton_0; "button"
0x1800bf90a  mov     [rsp+158h+cchCount2], r9d; cchCount2
0x1800bf90f  lea     r8, [rsp+158h+ClassName]; lpString1
0x1800bf914  mov     [rsp+158h+lpString2], rax; lpString2
0x1800bf919  lea     ebp, [r9+2]
0x1800bf91d  mov     edx, ebp; dwCmpFlags
0x1800bf91f  lea     ecx, [rbp+7Eh]; Locale
0x1800bf922  call    cs:__imp_CompareStringW
0x1800bf928  cmp     eax, 2
0x1800bf92b  jnz     short loc_1800BF97F
0x1800bf92d  lea     esi, [rbp-11h]
0x1800bf930  mov     rcx, rdi; hWnd
0x1800bf933  mov     edx, esi; nIndex
0x1800bf935  call    cs:__imp_GetWindowLongW
0x1800bf93b  and     eax, 0Fh
0x1800bf93e  cmp     eax, 4
0x1800bf941  jz      short loc_1800BF948
0x1800bf943  cmp     eax, 9
0x1800bf946  jnz     short loc_1800BF97F
0x1800bf948  mov     edx, esi; nIndex
0x1800bf94a  mov     rcx, rdi; hWnd
0x1800bf94d  call    cs:__imp_GetWindowLongW
0x1800bf953  mov     rcx, rdi; hWnd
0x1800bf956  bt      eax, 11h
0x1800bf95a  jb      short loc_1800BF971
0x1800bf95c  mov     edx, 3; uCmd
0x1800bf961  call    cs:__imp_GetWindow
0x1800bf967  mov     rdi, rax
0x1800bf96a  test    rax, rax
0x1800bf96d  jnz     short loc_1800BF948
0x1800bf96f  jmp     short loc_1800BF97F
0x1800bf971  mov     edx, 0FFFFFFF4h; nIndex
0x1800bf976  call    cs:__imp_GetWindowLongW
0x1800bf97c  mov     r12d, eax
0x1800bf97f  mov     r8d, ebp; int
0x1800bf982  mov     [rbx+0E8h], ebp
0x1800bf988  mov     edx, r12d; unsigned int
0x1800bf98b  mov     rcx, rbx; this
0x1800bf98e  call    ?SetControlStatus@COlePropertyPage@@QEAAHIH@Z; COlePropertyPage::SetControlStatus(uint,int)
0x1800bf993  lea     rcx, __ImageBase
0x1800bf99a  mov     esi, ebp
0x1800bf99c  jmp     short loc_1800BF9A3
0x1800bf99e  mov     ebp, 1
0x1800bf9a3  cmp     dword ptr [rbx+0E8h], 0
0x1800bf9aa  jz      short loc_1800BFA16
0x1800bf9ac  xor     edi, edi
0x1800bf9ae  lea     rax, [rsp+158h+ClassName]
0x1800bf9b3  movsxd  r15, edi
0x1800bf9b6  add     r15, r15
0x1800bf9b9  mov     [rsp+158h+cchCount2], 0FFFFFFFFh; cchCount2
0x1800bf9c1  or      r9d, 0FFFFFFFFh; cchCount1
0x1800bf9c5  mov     [rsp+158h+lpString2], rax; lpString2
0x1800bf9ca  mov     edx, ebp; dwCmpFlags
0x1800bf9cc  mov     r8, ds:rva ?_afxUpdateList@@3QBUNotifyInfo@@B[rcx+r15*8]; lpString1
0x1800bf9d4  mov     ecx, 7Fh; Locale
0x1800bf9d9  call    cs:__imp_CompareStringW
0x1800bf9df  lea     rcx, __ImageBase
0x1800bf9e6  cmp     eax, 2
0x1800bf9e9  jnz     short loc_1800BFA0F
0x1800bf9eb  cmp     ds:rva word_1800F0AA8[rcx+r15*8], r14w
0x1800bf9f4  jnz     short loc_1800BFA0F
0x1800bf9f6  mov     edx, r12d; unsigned int
0x1800bf9f9  mov     rcx, rbx; this
0x1800bf9fc  call    ?GetControlStatus@COlePropertyPage@@QEAAHI@Z; COlePropertyPage::GetControlStatus(uint)
0x1800bfa01  lea     rcx, __ImageBase
0x1800bfa08  test    eax, eax
0x1800bfa0a  jz      short loc_1800BFA0F
0x1800bfa0c  or      esi, 2
0x1800bfa0f  add     edi, ebp
0x1800bfa11  cmp     edi, 6
0x1800bfa14  jb      short loc_1800BF9AE
0x1800bfa16  test    esi, esi
0x1800bfa18  jz      short loc_1800BFA2F
0x1800bfa1a  mov     rcx, [rbx+120h]
0x1800bfa21  mov     edx, esi
0x1800bfa23  mov     rax, [rcx]
0x1800bfa26  mov     rax, [rax+18h]
0x1800bfa2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bfa2f  mov     eax, r13d
0x1800bfa32  mov     rcx, [rsp+158h+var_48]
0x1800bfa3a  xor     rcx, rsp; StackCookie
0x1800bfa3d  call    __security_check_cookie
0x1800bfa42  mov     rbx, [rsp+158h+arg_18]
0x1800bfa4a  add     rsp, 120h
0x1800bfa51  pop     r15
0x1800bfa53  pop     r14
0x1800bfa55  pop     r13
0x1800bfa57  pop     r12
0x1800bfa59  pop     rdi
0x1800bfa5a  pop     rsi
0x1800bfa5b  pop     rbp
0x1800bfa5c  retn
```
