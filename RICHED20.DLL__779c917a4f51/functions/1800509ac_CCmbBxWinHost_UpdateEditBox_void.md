# CCmbBxWinHost::UpdateEditBox(void)

- ea: `0x1800509ac`
- end: `0x180050abd`
- name: `?UpdateEditBox@CCmbBxWinHost@@QEAAXXZ`
- size: `273`
- prototype: `void __fastcall(CCmbBxWinHost *__hidden this)`
- caller_count: `3`
- callee_count: `7`
- tags: `loader_planting, installer_update`

## callers

- `0x18004e598`
- `0x18004e9e0`
- `0x18004f6e0`

## callees

- `0x180022780`
- `0x180023010`
- `0x18004d854`
- `0x18004dc20`
- `0x1800509ac`
- `0x180069ec0`
- `0x180092010`

## pseudocode

```c
void __fastcall CCmbBxWinHost::UpdateEditBox(HWND *this, __int64 a2, __int64 a3, unsigned __int64 a4)
{
  HWND v5; // rax
  void *v6; // rbp
  unsigned __int64 v7; // r14
  unsigned __int64 v8; // rcx
  unsigned int v9; // eax
  void *v10; // rax
  HDC v11; // rdx

  if ( *((_DWORD *)this + 60) == 3 && ((_BYTE)this[15] & 4) != 0 )
  {
    CCmbBxWinHost::CbMessageItemHandler((CCmbBxWinHost *)this, 0, 2, a4, 0);
    return;
  }
  v5 = this[31];
  v6 = 0;
  if ( *((_DWORD *)v5 + 50) != -1 )
  {
    v7 = *((int *)v5 + 50);
    v8 = (int)(RichListBoxWndProc(this[16], 0x18Au, v7, 0) + 1);
    v9 = 2 * v8;
    if ( !is_mul_ok(v8, 2u) )
      v9 = -1;
    v10 = CW32System::PvAlloc(v9, 0x40u);
    v6 = v10;
    if ( !v10 )
    {
      (*((void (__fastcall **)(HWND *, __int64, _QWORD))*this + 38))(this, 0xFFFFFFFFLL, 0);
      return;
    }
    RichListBoxWndProc(this[16], 0x189u, v7, (__int64)v10);
  }
  *((_DWORD *)this + 30) |= 0x1000u;
  (*(void (__fastcall **)(HWND, __int64))(*(_QWORD *)this[4] + 24LL))(this[4], 12);
  CCmbBxWinHost::DrawEditFocus((CCmbBxWinHost *)this, v11);
  if ( v6 )
    CW32System::FreePv(v6);
}

```

## disassembly

```asm
0x1800509ac  push    rbx
0x1800509ae  push    rbp
0x1800509af  push    rsi
0x1800509b0  push    rdi
0x1800509b1  push    r14
0x1800509b3  push    r15
0x1800509b5  sub     rsp, 38h
0x1800509b9  cmp     dword ptr [rcx+0F0h], 3
0x1800509c0  mov     rbx, rcx
0x1800509c3  jnz     short loc_1800509E2
0x1800509c5  test    byte ptr [rcx+78h], 4
0x1800509c9  jz      short loc_1800509E2
0x1800509cb  xor     edi, edi
0x1800509cd  xor     edx, edx; HDC
0x1800509cf  mov     [rsp+68h+var_48], rdi; __int64
0x1800509d4  lea     r8d, [rdi+2]; int
0x1800509d8  call    ?CbMessageItemHandler@CCmbBxWinHost@@QEAA_JPEAUHDC__@@H_K_J@Z; CCmbBxWinHost::CbMessageItemHandler(HDC__ *,int,unsigned __int64,__int64)
0x1800509dd  jmp     loc_180050AB0
0x1800509e2  mov     rax, [rcx+0F8h]
0x1800509e9  xor     edi, edi
0x1800509eb  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800509ef  mov     ebp, edi
0x1800509f1  movsxd  rcx, dword ptr [rax+0C8h]
0x1800509f8  cmp     ecx, r15d
0x1800509fb  jz      short loc_180050A69
0x1800509fd  mov     r14, rcx
0x180050a00  mov     r8, rcx; unsigned __int64
0x180050a03  mov     rcx, [rbx+80h]; HWND
0x180050a0a  xor     r9d, r9d; __int64
0x180050a0d  mov     edx, 18Ah; unsigned int
0x180050a12  call    ?RichListBoxWndProc@@YA_JPEAUHWND__@@I_K_J@Z; RichListBoxWndProc(HWND__ *,uint,unsigned __int64,__int64)
0x180050a17  inc     eax
0x180050a19  movsxd  rcx, eax
0x180050a1c  lea     eax, [rdi+2]
0x180050a1f  mul     rcx
0x180050a22  lea     edx, [rdi+40h]; unsigned int
0x180050a25  cmovb   rax, r15
0x180050a29  mov     ecx, eax; unsigned int
0x180050a2b  call    ?PvAlloc@CW32System@@SAPEAXKI@Z; CW32System::PvAlloc(ulong,uint)
0x180050a30  mov     rbp, rax
0x180050a33  test    rax, rax
0x180050a36  jnz     short loc_180050A52
0x180050a38  mov     rax, [rbx]
0x180050a3b  xor     r8d, r8d
0x180050a3e  or      edx, 0FFFFFFFFh
0x180050a41  mov     rcx, rbx
0x180050a44  mov     rax, [rax+130h]
0x180050a4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050a50  jmp     short loc_180050AB0
0x180050a52  mov     rcx, [rbx+80h]; HWND
0x180050a59  mov     r9, rax; __int64
0x180050a5c  mov     r8, r14; unsigned __int64
0x180050a5f  mov     edx, 189h; unsigned int
0x180050a64  call    ?RichListBoxWndProc@@YA_JPEAUHWND__@@I_K_J@Z; RichListBoxWndProc(HWND__ *,uint,unsigned __int64,__int64)
0x180050a69  bts     dword ptr [rbx+78h], 0Ch
0x180050a6e  lea     r9, [rsp+68h+arg_0]
0x180050a73  mov     rcx, [rbx+20h]
0x180050a77  test    rbp, rbp
0x180050a7a  mov     [rsp+68h+arg_0], di
0x180050a7f  cmovnz  r9, rbp
0x180050a83  mov     [rsp+68h+var_48], rdi
0x180050a88  xor     r8d, r8d
0x180050a8b  mov     rax, [rcx]
0x180050a8e  lea     edx, [r8+0Ch]
0x180050a92  mov     rax, [rax+18h]
0x180050a96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050a9b  mov     rcx, rbx; this
0x180050a9e  call    ?DrawEditFocus@CCmbBxWinHost@@QEAAXPEAUHDC__@@@Z; CCmbBxWinHost::DrawEditFocus(HDC__ *)
0x180050aa3  test    rbp, rbp
0x180050aa6  jz      short loc_180050AB0
0x180050aa8  mov     rcx, rbp; lpMem
0x180050aab  call    ?FreePv@CW32System@@SAXPEAX@Z; CW32System::FreePv(void *)
0x180050ab0  add     rsp, 38h
0x180050ab4  pop     r15
0x180050ab6  pop     r14
0x180050ab8  pop     rdi
0x180050ab9  pop     rsi
0x180050aba  pop     rbp
0x180050abb  pop     rbx
0x180050abc  retn
```
