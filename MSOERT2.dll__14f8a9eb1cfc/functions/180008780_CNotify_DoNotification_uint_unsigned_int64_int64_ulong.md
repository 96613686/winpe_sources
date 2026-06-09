# CNotify::DoNotification(uint,unsigned __int64,__int64,ulong)

- ea: `0x180008780`
- end: `0x1800089bb`
- name: `?DoNotification@CNotify@@UEAAJI_K_JK@Z`
- size: `571`
- prototype: `int(CNotify *__hidden this, unsigned int, unsigned __int64, __int64, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation`

## callees

- `0x180008780`
- `0x180012f8e`
- `0x180012fc0`
- `0x180014010`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x1800087da`
- `KERNEL32!GetCurrentProcessId` at `0x1800087da`
- `USER32!SendMessageA` at `0x18000895f`
- `USER32!SendMessageA` at `0x18000895f`
- `USER32!IsWindow` at `0x180008806`
- `USER32!IsWindow` at `0x180008806`
- `USER32!GetWindowThreadProcessId` at `0x180008828`
- `USER32!GetWindowThreadProcessId` at `0x180008828`
- `USER32!SendMessageTimeoutA` at `0x180008901`
- `USER32!SendMessageTimeoutA` at `0x180008901`
- `USER32!PostMessageA` at `0x180008983`
- `USER32!PostMessageA` at `0x180008983`

## pseudocode

```c
__int64 __fastcall CNotify::DoNotification(
        CNotify *this,
        UINT a2,
        __int64 (__fastcall *a3)(LPARAM, __int64 *, bool, _QWORD),
        LPARAM a4,
        unsigned int a5)
{
  int v7; // r15d
  DWORD CurrentProcessId; // eax
  unsigned int *v9; // rbx
  unsigned int v10; // esi
  HWND v11; // rcx
  HWND v12; // rcx
  LPARAM v13; // r9
  WPARAM v14; // r8
  UINT v15; // edx
  char v16; // al
  HWND v17; // rcx
  DWORD dwProcessId; // [rsp+40h] [rbp-C0h] BYREF
  DWORD i; // [rsp+44h] [rbp-BCh]
  UINT Msg; // [rsp+48h] [rbp-B8h]
  LPARAM v22; // [rsp+50h] [rbp-B0h]
  ULONG_PTR dwResult; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v24; // [rsp+60h] [rbp-A0h] BYREF
  UINT v25; // [rsp+68h] [rbp-98h]
  __int64 (__fastcall *v26)(_QWORD, _QWORD, _QWORD, _QWORD); // [rsp+70h] [rbp-90h]
  LPARAM v27; // [rsp+78h] [rbp-88h]
  int v28; // [rsp+80h] [rbp-80h]
  LPARAM lParam[2]; // [rsp+298h] [rbp+198h] BYREF
  __int64 v30; // [rsp+2A8h] [rbp+1A8h]

  Msg = a2;
  dwProcessId = 0;
  dwResult = 0;
  v22 = a4;
  v7 = 0;
  memset_0(&v24, 0, 0x250u);
  CurrentProcessId = GetCurrentProcessId();
  v9 = (unsigned int *)*((_QWORD *)this + 4);
  v10 = 0;
  for ( i = CurrentProcessId; v10 < *v9; ++v10 )
  {
    v11 = *(HWND *)&v9[6 * v10 + 4];
    if ( v11 )
    {
      if ( IsWindow(v11) )
      {
        v12 = *(HWND *)&v9[6 * v10 + 4];
        if ( *((HWND *)this + 6) != v12 )
        {
          GetWindowThreadProcessId(v12, &dwProcessId);
          memset_0(&v24, 0, 0x250u);
          v24 = *(_QWORD *)&v9[6 * v10 + 4];
          if ( (a5 & 2) != 0 )
          {
            v7 = a3(v22, &v24, i != dwProcessId, v9[6 * v10 + 6]);
            if ( v7 < 0 )
              return (unsigned int)v7;
            v13 = v27;
            v14 = (WPARAM)v26;
            v15 = v25;
          }
          else
          {
            v13 = v22;
            v14 = (WPARAM)a3;
            v15 = Msg;
            v27 = v22;
            v25 = Msg;
            v26 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))a3;
          }
          v16 = a5 | v28;
          v28 |= a5;
          if ( i == dwProcessId )
          {
LABEL_16:
            v17 = *(HWND *)&v9[6 * v10 + 4];
            if ( (a5 & 1) != 0 )
            {
              if ( SendMessageA(v17, v15, v14, v13) == 4294967280LL )
              {
                *(_QWORD *)&v9[6 * v10 + 4] = 0;
                *(_QWORD *)&v9[6 * v10 + 2] = 0;
              }
            }
            else
            {
              PostMessageA(v17, v15, v14, v13);
            }
            goto LABEL_20;
          }
          if ( (v16 & 4) != 0 )
          {
            if ( (v16 & 8) == 0 )
              goto LABEL_16;
            SendMessageTimeoutA(*(HWND *)&v9[6 * v10 + 2], 0x4Au, 0, (LPARAM)lParam, 2u, 0x5DCu, &dwResult);
            if ( dwResult == 4294967280 )
            {
              *(_QWORD *)&v9[6 * v10 + 4] = 0;
              *(_QWORD *)&v9[6 * v10 + 2] = 0;
            }
            if ( v30 )
            {
              ((void (__fastcall *)(LPMALLOC))g_pMalloc->lpVtbl->Free)(g_pMalloc);
              v30 = 0;
            }
          }
        }
      }
    }
LABEL_20:
    v9 = (unsigned int *)*((_QWORD *)this + 4);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180008780  push    rbp
0x180008782  push    rbx
0x180008783  push    rsi
0x180008784  push    rdi
0x180008785  push    r12
0x180008787  push    r13
0x180008789  push    r15
0x18000878b  lea     rbp, [rsp-1C0h]
0x180008793  sub     rsp, 2C0h
0x18000879a  mov     rax, cs:__security_cookie
0x1800087a1  xor     rax, rsp
0x1800087a4  mov     [rbp+1F0h+var_40], rax
0x1800087ab  xor     edi, edi
0x1800087ad  mov     [rsp+2F0h+Msg], edx
0x1800087b1  mov     r12, r8
0x1800087b4  mov     [rsp+2F0h+dwProcessId], edi
0x1800087b8  mov     r13, rcx
0x1800087bb  mov     [rsp+2F0h+dwResult], rdi
0x1800087c0  xor     edx, edx; Val
0x1800087c2  mov     [rsp+2F0h+var_2A0], r9
0x1800087c7  mov     r8d, 250h; Size
0x1800087cd  lea     rcx, [rsp+2F0h+var_290]; void *
0x1800087d2  mov     r15d, edi
0x1800087d5  call    memset_0
0x1800087da  call    cs:__imp_GetCurrentProcessId
0x1800087e0  mov     rbx, [r13+20h]
0x1800087e4  mov     esi, edi
0x1800087e6  mov     [rsp+2F0h+var_2AC], eax
0x1800087ea  cmp     [rbx], edi
0x1800087ec  jbe     loc_180008997
0x1800087f2  mov     eax, esi
0x1800087f4  lea     rdi, [rax+rax*2]
0x1800087f8  mov     rcx, [rbx+rdi*8+10h]; hWnd
0x1800087fd  test    rcx, rcx
0x180008800  jz      loc_180008989
0x180008806  call    cs:__imp_IsWindow
0x18000880c  test    eax, eax
0x18000880e  jz      loc_180008989
0x180008814  mov     rcx, [rbx+rdi*8+10h]; hWnd
0x180008819  cmp     [r13+30h], rcx
0x18000881d  jz      loc_180008989
0x180008823  lea     rdx, [rsp+2F0h+dwProcessId]; lpdwProcessId
0x180008828  call    cs:__imp_GetWindowThreadProcessId
0x18000882e  xor     edx, edx; Val
0x180008830  lea     rcx, [rsp+2F0h+var_290]; void *
0x180008835  mov     r8d, 250h; Size
0x18000883b  call    memset_0
0x180008840  test    byte ptr [rbp+1F0h+arg_20], 2
0x180008847  mov     rax, [rbx+rdi*8+10h]
0x18000884c  mov     [rsp+2F0h+var_290], rax
0x180008851  jz      short loc_180008894
0x180008853  mov     eax, [rsp+2F0h+var_2AC]
0x180008857  lea     rdx, [rsp+2F0h+var_290]
0x18000885c  mov     r9d, [rbx+rdi*8+18h]
0x180008861  xor     r8d, r8d
0x180008864  cmp     eax, [rsp+2F0h+dwProcessId]
0x180008868  mov     rax, r12
0x18000886b  mov     rcx, [rsp+2F0h+var_2A0]
0x180008870  setnz   r8b
0x180008874  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008879  mov     r15d, eax
0x18000887c  test    eax, eax
0x18000887e  js      loc_180008997
0x180008884  mov     r9, [rsp+2F0h+var_278]
0x180008889  mov     r8, [rsp+2F0h+var_280]
0x18000888e  mov     edx, [rsp+2F0h+var_288]
0x180008892  jmp     short loc_1800088AE
0x180008894  mov     r9, [rsp+2F0h+var_2A0]; lParam
0x180008899  mov     r8, r12; wParam
0x18000889c  mov     edx, [rsp+2F0h+Msg]; Msg
0x1800088a0  mov     [rsp+2F0h+var_278], r9
0x1800088a5  mov     [rsp+2F0h+var_288], edx
0x1800088a9  mov     [rsp+2F0h+var_280], r12
0x1800088ae  mov     eax, [rbp+1F0h+var_270]
0x1800088b1  or      eax, [rbp+1F0h+arg_20]
0x1800088b7  mov     ecx, [rsp+2F0h+var_2AC]
0x1800088bb  mov     [rbp+1F0h+var_270], eax
0x1800088be  cmp     ecx, [rsp+2F0h+dwProcessId]
0x1800088c2  jz      loc_180008951
0x1800088c8  test    al, 4
0x1800088ca  jz      loc_180008989
0x1800088d0  test    al, 8
0x1800088d2  jz      short loc_180008951
0x1800088d4  mov     rcx, [rbx+rdi*8+8]; hWnd
0x1800088d9  lea     rax, [rsp+2F0h+dwResult]
0x1800088de  mov     [rsp+2F0h+lpdwResult], rax; lpdwResult
0x1800088e3  lea     r9, [rbp+1F0h+lParam]; lParam
0x1800088ea  xor     r8d, r8d; wParam
0x1800088ed  mov     [rsp+2F0h+uTimeout], 5DCh; uTimeout
0x1800088f5  mov     [rsp+2F0h+fuFlags], 2; fuFlags
0x1800088fd  lea     edx, [r8+4Ah]; Msg
0x180008901  call    cs:__imp_SendMessageTimeoutA
0x180008907  mov     eax, 0FFFFFFF0h
0x18000890c  cmp     [rsp+2F0h+dwResult], rax
0x180008911  jnz     short loc_180008925
0x180008913  mov     qword ptr [rbx+rdi*8+10h], 0
0x18000891c  mov     qword ptr [rbx+rdi*8+8], 0
0x180008925  mov     rdx, [rbp+1F0h+var_48]
0x18000892c  test    rdx, rdx
0x18000892f  jz      short loc_180008989
0x180008931  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x180008938  mov     rax, [rcx]
0x18000893b  mov     rax, [rax+28h]
0x18000893f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008944  mov     [rbp+1F0h+var_48], 0
0x18000894f  jmp     short loc_180008989
0x180008951  test    byte ptr [rbp+1F0h+arg_20], 1
0x180008958  mov     rcx, [rbx+rdi*8+10h]; hWnd
0x18000895d  jz      short loc_180008983
0x18000895f  call    cs:__imp_SendMessageA
0x180008965  mov     ecx, 0FFFFFFF0h
0x18000896a  cmp     rax, rcx
0x18000896d  jnz     short loc_180008989
0x18000896f  mov     qword ptr [rbx+rdi*8+10h], 0
0x180008978  mov     qword ptr [rbx+rdi*8+8], 0
0x180008981  jmp     short loc_180008989
0x180008983  call    cs:__imp_PostMessageA
0x180008989  mov     rbx, [r13+20h]
0x18000898d  inc     esi
0x18000898f  cmp     esi, [rbx]
0x180008991  jb      loc_1800087F2
0x180008997  mov     eax, r15d
0x18000899a  mov     rcx, [rbp+1F0h+var_40]
0x1800089a1  xor     rcx, rsp; StackCookie
0x1800089a4  call    __security_check_cookie
0x1800089a9  add     rsp, 2C0h
0x1800089b0  pop     r15
0x1800089b2  pop     r13
0x1800089b4  pop     r12
0x1800089b6  pop     rdi
0x1800089b7  pop     rsi
0x1800089b8  pop     rbx
0x1800089b9  pop     rbp
0x1800089ba  retn
```
