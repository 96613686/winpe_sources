# FrameWindow::OnBrowserToolCreated(uint,unsigned __int64,__int64,int &)

- ea: `0x1800232e8`
- end: `0x1800234d2`
- name: `?OnBrowserToolCreated@FrameWindow@@QEAA_JI_K_JAEAH@Z`
- size: `490`
- prototype: `__int64 __fastcall(FrameWindow *__hidden this, unsigned int, unsigned __int64, __int64, int *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18002b910`

## callees

- `0x180001800`
- `0x1800227a0`
- `0x1800232e8`
- `0x1800282e0`
- `0x180028a60`
- `0x180028d38`
- `0x180035010`

## import_xrefs

- `USER32!GetClientRect` at `0x1800233b4`
- `USER32!GetClientRect` at `0x1800233b4`
- `USER32!EnableWindow` at `0x18002341a`
- `USER32!EnableWindow` at `0x18002341a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall FrameWindow::OnBrowserToolCreated(FrameWindow *this, __int64 a2, signed int a3, HWND a4)
{
  __int64 *v7; // rcx
  __int64 *v8; // rax
  __int64 *v9; // rbx
  __int64 v10; // rax
  __int64 *v11; // r14
  volatile signed __int32 *v12; // rbx
  __int64 v13; // rax
  __int64 v15; // [rsp+20h] [rbp-68h]
  struct tagRECT Rect; // [rsp+40h] [rbp-48h] BYREF

  v7 = (__int64 *)*((_QWORD *)this + 56);
  v8 = (__int64 *)v7[1];
  v9 = v7;
  while ( !*((_BYTE *)v8 + 25) )
  {
    if ( *((_DWORD *)v8 + 8) >= a3 )
      v9 = v8;
    else
      v8 += 2;
    v8 = (__int64 *)*v8;
  }
  if ( *((_BYTE *)v9 + 25) || a3 < *((_DWORD *)v9 + 8) || v9 == v7 || !v9[5] )
    return -1;
  v10 = v9[6];
  if ( v10 )
    _InterlockedIncrement((volatile signed __int32 *)(v10 + 8));
  v11 = (__int64 *)v9[5];
  v12 = (volatile signed __int32 *)v9[6];
  v13 = *v11;
  if ( !*v11 )
  {
    if ( v12 )
    {
      if ( _InterlockedExchangeAdd(v12 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v12)(v12);
        if ( _InterlockedExchangeAdd(v12 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
      }
    }
    return -1;
  }
  if ( !*(_QWORD *)(v13 + 32) )
    *(_QWORD *)(v13 + 32) = a4;
  v11[2] = (__int64)a4;
  if ( (!a3 || a3 == *((_DWORD *)this + 138))
    && (GetClientRect(*((HWND *)this + 1), &Rect),
        LODWORD(v15) = Rect.right - Rect.left,
        HIDWORD(v15) = Rect.bottom - Rect.top,
        FrameWindow::Resize(this, v15),
        !a3)
    || a3 == 8 )
  {
    EnableWindow(a4, 1);
  }
  else if ( a3 == *((_DWORD *)this + 138) )
  {
    FrameWindow::ShowSelectedTool(this);
  }
  else if ( a3 == 1 && *((_BYTE *)this + 438) )
  {
    FrameWindow::ShowHideConsole(this);
  }
  if ( *((_BYTE *)v11 + 24) )
    FrameWindow::FirePendingMessages((__int64)this, (unsigned int)a3);
  if ( v12 && _InterlockedExchangeAdd(v12 + 2, 0xFFFFFFFF) == 1 )
  {
    (**(void (__fastcall ***)(volatile signed __int32 *))v12)(v12);
    if ( _InterlockedExchangeAdd(v12 + 3, 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
  }
  return 0;
}

```

## disassembly

```asm
0x1800232e8  mov     [rsp+arg_8], rbx
0x1800232ed  push    rbp
0x1800232ee  push    rsi
0x1800232ef  push    rdi
0x1800232f0  push    r12
0x1800232f2  push    r14
0x1800232f4  sub     rsp, 60h
0x1800232f8  mov     rax, cs:__security_cookie
0x1800232ff  xor     rax, rsp
0x180023302  mov     [rsp+88h+var_38], rax
0x180023307  mov     rbp, r9
0x18002330a  mov     rdi, r8
0x18002330d  mov     rsi, rcx
0x180023310  mov     rcx, [rcx+1C0h]
0x180023317  mov     rax, [rcx+8]
0x18002331b  xor     edx, edx
0x18002331d  mov     [rsp+88h+var_54], edx
0x180023321  mov     rbx, rcx
0x180023324  jmp     short loc_180023337
0x180023326  cmp     [rax+20h], edi
0x180023329  jge     short loc_180023331
0x18002332b  add     rax, 10h
0x18002332f  jmp     short loc_180023334
0x180023331  mov     rbx, rax
0x180023334  mov     rax, [rax]
0x180023337  cmp     [rax+19h], dl
0x18002333a  jz      short loc_180023326
0x18002333c  or      r12, 0FFFFFFFFFFFFFFFFh
0x180023340  cmp     [rbx+19h], dl
0x180023343  jnz     loc_1800234AE
0x180023349  cmp     edi, [rbx+20h]
0x18002334c  jl      loc_1800234AE
0x180023352  cmp     rbx, rcx
0x180023355  jz      loc_1800234AE
0x18002335b  cmp     [rbx+28h], rdx
0x18002335f  jz      loc_1800234AE
0x180023365  mov     rax, [rbx+30h]
0x180023369  test    rax, rax
0x18002336c  jz      short loc_180023372
0x18002336e  lock inc dword ptr [rax+8]
0x180023372  mov     r14, [rbx+28h]
0x180023376  mov     [rsp+88h+var_60], r14
0x18002337b  mov     rbx, [rbx+30h]
0x18002337f  mov     [rsp+30h], rbx
0x180023384  mov     rax, [r14]
0x180023387  test    rax, rax
0x18002338a  jz      loc_180023472
0x180023390  cmp     qword ptr [rax+20h], 0
0x180023395  jnz     short loc_18002339B
0x180023397  mov     [rax+20h], rbp
0x18002339b  mov     [r14+10h], rbp
0x18002339f  test    edi, edi
0x1800233a1  jz      short loc_1800233AB
0x1800233a3  cmp     edi, [rsi+228h]
0x1800233a9  jnz     short loc_1800233E3
0x1800233ab  lea     rdx, [rsp+88h+Rect]; lpRect
0x1800233b0  mov     rcx, [rsi+8]; hWnd
0x1800233b4  call    cs:__imp_GetClientRect
0x1800233ba  mov     eax, [rsp+88h+Rect.right]
0x1800233be  sub     eax, [rsp+88h+Rect.left]
0x1800233c2  mov     dword ptr [rsp+88h+var_68], eax
0x1800233c6  mov     eax, [rsp+88h+Rect.bottom]
0x1800233ca  sub     eax, [rsp+88h+Rect.top]
0x1800233ce  mov     dword ptr [rsp+88h+var_68+4], eax
0x1800233d2  mov     rdx, [rsp+88h+var_68]
0x1800233d7  mov     rcx, rsi
0x1800233da  call    ?Resize@FrameWindow@@AEAAXVCSize@@@Z; FrameWindow::Resize(CSize)
0x1800233df  test    edi, edi
0x1800233e1  jz      short loc_180023412
0x1800233e3  cmp     edi, 8
0x1800233e6  jz      short loc_180023412
0x1800233e8  cmp     edi, [rsi+228h]
0x1800233ee  jnz     short loc_1800233FA
0x1800233f0  mov     rcx, rsi; this
0x1800233f3  call    ?ShowSelectedTool@FrameWindow@@AEAAJXZ; FrameWindow::ShowSelectedTool(void)
0x1800233f8  jmp     short loc_180023420
0x1800233fa  cmp     edi, 1
0x1800233fd  jnz     short loc_180023420
0x1800233ff  cmp     byte ptr [rsi+1B6h], 0
0x180023406  jz      short loc_180023420
0x180023408  mov     rcx, rsi; this
0x18002340b  call    ?ShowHideConsole@FrameWindow@@AEAAXXZ; FrameWindow::ShowHideConsole(void)
0x180023410  jmp     short loc_180023420
0x180023412  mov     edx, 1; bEnable
0x180023417  mov     rcx, rbp; hWnd
0x18002341a  call    cs:__imp_EnableWindow
0x180023420  cmp     byte ptr [r14+18h], 0
0x180023425  jz      short loc_180023432
0x180023427  mov     edx, edi
0x180023429  mov     rcx, rsi
0x18002342c  call    ?FirePendingMessages@FrameWindow@@AEAAXW4PluginId@@@Z; FrameWindow::FirePendingMessages(PluginId)
0x180023431  nop
0x180023432  test    rbx, rbx
0x180023435  jz      short loc_18002346E
0x180023437  mov     eax, r12d
0x18002343a  lock xadd [rbx+8], eax
0x18002343f  add     eax, r12d
0x180023442  jnz     short loc_18002346E
0x180023444  mov     rax, [rbx]
0x180023447  mov     rcx, rbx
0x18002344a  mov     rax, [rax]
0x18002344d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023452  mov     eax, r12d
0x180023455  lock xadd [rbx+0Ch], eax
0x18002345a  add     eax, r12d
0x18002345d  jnz     short loc_18002346E
0x18002345f  mov     rax, [rbx]
0x180023462  mov     rcx, rbx
0x180023465  mov     rax, [rax+8]
0x180023469  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002346e  xor     eax, eax
0x180023470  jmp     short loc_1800234B1
0x180023472  test    rbx, rbx
0x180023475  jz      short loc_1800234AE
0x180023477  mov     eax, r12d
0x18002347a  lock xadd [rbx+8], eax
0x18002347f  add     eax, r12d
0x180023482  jnz     short loc_1800234AE
0x180023484  mov     rax, [rbx]
0x180023487  mov     rcx, rbx
0x18002348a  mov     rax, [rax]
0x18002348d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023492  mov     ecx, r12d
0x180023495  lock xadd [rbx+0Ch], ecx
0x18002349a  add     ecx, r12d
0x18002349d  jnz     short loc_1800234AE
0x18002349f  mov     rcx, [rbx]
0x1800234a2  mov     rax, [rcx+8]
0x1800234a6  mov     rcx, rbx
0x1800234a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800234ae  mov     rax, r12
0x1800234b1  mov     rcx, [rsp+88h+var_38]
0x1800234b6  xor     rcx, rsp; StackCookie
0x1800234b9  call    __security_check_cookie
0x1800234be  mov     rbx, [rsp+88h+arg_8]
0x1800234c6  add     rsp, 60h
0x1800234ca  pop     r14
0x1800234cc  pop     r12
0x1800234ce  pop     rdi
0x1800234cf  pop     rsi
0x1800234d0  pop     rbp
0x1800234d1  retn
```
