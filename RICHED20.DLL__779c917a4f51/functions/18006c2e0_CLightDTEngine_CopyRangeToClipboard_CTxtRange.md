# CLightDTEngine::CopyRangeToClipboard(CTxtRange *)

- ea: `0x18006c2e0`
- end: `0x18006c4b8`
- name: `?CopyRangeToClipboard@CLightDTEngine@@QEAAJPEAVCTxtRange@@@Z`
- size: `472`
- prototype: `__int64 __fastcall(CLightDTEngine *__hidden this, struct CTxtRange *)`
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x18005b8dc`
- `0x1800878c0`

## callees

- `0x18003c4f4`
- `0x18003ffa8`
- `0x180040f98`
- `0x1800490f0`
- `0x18006c2e0`
- `0x18006d38c`
- `0x18008ffc8`
- `0x180092010`

## import_xrefs

- `USER32!OpenClipboard` at `0x18006c40d`
- `USER32!OpenClipboard` at `0x18006c40d`
- `USER32!EmptyClipboard` at `0x18006c417`
- `USER32!EmptyClipboard` at `0x18006c417`
- `USER32!SetClipboardData` at `0x18006c42a`
- `USER32!SetClipboardData` at `0x18006c435`
- `USER32!SetClipboardData` at `0x18006c453`
- `USER32!SetClipboardData` at `0x18006c462`
- `USER32!SetClipboardData` at `0x18006c46d`
- `USER32!SetClipboardData` at `0x18006c47c`
- `USER32!SetClipboardData` at `0x18006c42a`
- `USER32!SetClipboardData` at `0x18006c435`
- `USER32!SetClipboardData` at `0x18006c453`
- `USER32!SetClipboardData` at `0x18006c462`
- `USER32!SetClipboardData` at `0x18006c46d`
- `USER32!SetClipboardData` at `0x18006c47c`
- `USER32!CloseClipboard` at `0x18006c482`
- `USER32!CloseClipboard` at `0x18006c482`

## pseudocode

```c
__int64 __fastcall CLightDTEngine::CopyRangeToClipboard(CTxtEdit **this, struct CTxtRange *a2)
{
  CTxtEdit *v2; // r12
  _QWORD *v5; // r14
  int v6; // ebx
  CObjectMgr *v8; // r12
  int IndexForCp; // edi
  BOOL v10; // edi
  unsigned int v11; // ebx
  CTxtEdit *v12; // rcx
  CTxtEdit *v13; // rcx
  __int64 v14; // [rsp+70h] [rbp+40h] BYREF
  struct IDataObject *v15; // [rsp+80h] [rbp+50h] BYREF
  HWND hWndNewOwner; // [rsp+88h] [rbp+58h] BYREF

  v2 = *this;
  v15 = 0;
  v5 = (_QWORD *)*((_QWORD *)v2 + 17);
  if ( v5 )
    v5 = (_QWORD *)v5[4];
  v14 = 0;
  CTxtRange::GetRange(a2, (int *)&v14, (int *)&v14 + 1);
  v6 = v14;
  if ( (int)v14 >= SHIDWORD(v14) )
    return 0;
  v10 = 0;
  if ( HIDWORD(v14) - (_DWORD)v14 == 1 )
  {
    v8 = (CObjectMgr *)*((_QWORD *)v2 + 17);
    if ( v8 )
    {
      IndexForCp = CObjectMgr::FindIndexForCp(v8, SHIDWORD(v14));
      if ( IndexForCp != (unsigned int)CObjectMgr::FindIndexForCp(v8, v6) )
        v10 = 1;
    }
  }
  if ( v5 )
  {
    v11 = (*(__int64 (__fastcall **)(_QWORD *, __int64 *, __int64, struct IDataObject **))(*v5 + 80LL))(
            v5,
            &v14,
            2,
            &v15);
    if ( !v11 )
      goto LABEL_15;
  }
  if ( !*((_DWORD *)a2 + 22) )
  {
    CTxtEdit::Beep(*this);
    return 0;
  }
  v11 = CLightDTEngine::RangeToDataObject((CLightDTEngine *)this, a2, 3, &v15);
  if ( !v11 )
  {
LABEL_15:
    if ( v15 )
    {
      v11 = CW32System::OleSetClipboard(v15);
      if ( v11 )
      {
        v12 = *this;
        hWndNewOwner = 0;
        *((_BYTE *)this + 25) = 1;
        if ( !(unsigned int)CTxtEdit::TxGetWindow(v12, &hWndNewOwner) && OpenClipboard(hWndNewOwner) && EmptyClipboard() )
        {
          SetClipboardData((unsigned __int16)xmmword_1800A30F0, 0);
          SetClipboardData(0xDu, 0);
          if ( (*((_DWORD *)*this + 48) & 0xFF8FFEFF) != 0 )
          {
            SetClipboardData((unsigned __int16)g_rgFETC, 0);
            SetClipboardData((unsigned __int16)xmmword_1800A3110, 0);
          }
          SetClipboardData(1u, 0);
          if ( v10 )
            SetClipboardData(8u, 0);
          CloseClipboard();
          v11 = 0;
        }
      }
      v13 = this[2];
      if ( v13 )
        (*(void (__fastcall **)(CTxtEdit *))(*(_QWORD *)v13 + 16LL))(v13);
      this[2] = (CTxtEdit *)v15;
    }
  }
  return v11;
}

```

## disassembly

```asm
0x18006c2e0  push    rbp
0x18006c2e2  push    rbx
0x18006c2e3  push    rsi
0x18006c2e4  push    rdi
0x18006c2e5  push    r12
0x18006c2e7  push    r14
0x18006c2e9  push    r15
0x18006c2eb  mov     rbp, rsp
0x18006c2ee  sub     rsp, 30h
0x18006c2f2  mov     r12, [rcx]
0x18006c2f5  mov     r15, rdx
0x18006c2f8  mov     [rbp+arg_10], 0
0x18006c300  mov     rsi, rcx
0x18006c303  mov     r14, [r12+88h]
0x18006c30b  test    r14, r14
0x18006c30e  jz      short loc_18006C314
0x18006c310  mov     r14, [r14+20h]
0x18006c314  lea     r8, [rbp+arg_4]; int *
0x18006c318  mov     qword ptr [rbp+40h], 0
0x18006c320  lea     rdx, [rbp+arg_0]; int *
0x18006c324  mov     rcx, r15; this
0x18006c327  call    ?GetRange@CTxtRange@@QEBAJAEAJ0@Z; CTxtRange::GetRange(long &,long &)
0x18006c32c  mov     rbx, qword ptr [rbp+arg_0]
0x18006c330  mov     edx, [rbp+arg_4]; int
0x18006c333  cmp     ebx, edx
0x18006c335  jl      short loc_18006C33E
0x18006c337  xor     eax, eax
0x18006c339  jmp     loc_18006C4A9
0x18006c33e  mov     eax, edx
0x18006c340  sub     eax, ebx
0x18006c342  cmp     eax, 1
0x18006c345  jnz     short loc_18006C373
0x18006c347  mov     r12, [r12+88h]
0x18006c34f  test    r12, r12
0x18006c352  jz      short loc_18006C373
0x18006c354  mov     rcx, r12; this
0x18006c357  call    ?FindIndexForCp@CObjectMgr@@QEAAJJ@Z; CObjectMgr::FindIndexForCp(long)
0x18006c35c  mov     edx, ebx; int
0x18006c35e  mov     rcx, r12; this
0x18006c361  mov     edi, eax
0x18006c363  call    ?FindIndexForCp@CObjectMgr@@QEAAJJ@Z; CObjectMgr::FindIndexForCp(long)
0x18006c368  cmp     edi, eax
0x18006c36a  jz      short loc_18006C373
0x18006c36c  mov     edi, 1
0x18006c371  jmp     short loc_18006C375
0x18006c373  xor     edi, edi
0x18006c375  test    r14, r14
0x18006c378  jz      short loc_18006C39D
0x18006c37a  mov     rax, [r14]
0x18006c37d  lea     r9, [rbp+arg_10]
0x18006c381  mov     r8d, 2
0x18006c387  lea     rdx, [rbp+arg_0]
0x18006c38b  mov     rcx, r14
0x18006c38e  mov     rax, [rax+50h]
0x18006c392  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c397  mov     ebx, eax
0x18006c399  test    eax, eax
0x18006c39b  jz      short loc_18006C3CD
0x18006c39d  cmp     dword ptr [r15+58h], 0
0x18006c3a2  jnz     short loc_18006C3AE
0x18006c3a4  mov     rcx, [rsi]; this
0x18006c3a7  call    ?Beep@CTxtEdit@@QEAAXXZ; CTxtEdit::Beep(void)
0x18006c3ac  jmp     short loc_18006C337
0x18006c3ae  lea     r9, [rbp+arg_10]; struct IDataObject **
0x18006c3b2  mov     r8d, 3; int
0x18006c3b8  mov     rdx, r15; struct CTxtRange *
0x18006c3bb  mov     rcx, rsi; this
0x18006c3be  call    ?RangeToDataObject@CLightDTEngine@@QEAAJPEAVCTxtRange@@JPEAPEAUIDataObject@@@Z; CLightDTEngine::RangeToDataObject(CTxtRange *,long,IDataObject * *)
0x18006c3c3  mov     ebx, eax
0x18006c3c5  test    eax, eax
0x18006c3c7  jnz     loc_18006C4A7
0x18006c3cd  mov     rcx, [rbp+arg_10]; struct IDataObject *
0x18006c3d1  test    rcx, rcx
0x18006c3d4  jz      loc_18006C4A7
0x18006c3da  call    ?OleSetClipboard@CW32System@@SAJPEAUIDataObject@@@Z; CW32System::OleSetClipboard(IDataObject *)
0x18006c3df  mov     ebx, eax
0x18006c3e1  test    eax, eax
0x18006c3e3  jz      loc_18006C48A
0x18006c3e9  mov     rcx, [rsi]; this
0x18006c3ec  lea     rdx, [rbp+hWndNewOwner]; HWND *
0x18006c3f0  mov     [rbp+hWndNewOwner], 0
0x18006c3f8  mov     byte ptr [rsi+19h], 1
0x18006c3fc  call    ?TxGetWindow@CTxtEdit@@QEAAJPEAPEAUHWND__@@@Z; CTxtEdit::TxGetWindow(HWND__ * *)
0x18006c401  test    eax, eax
0x18006c403  jnz     loc_18006C48A
0x18006c409  mov     rcx, [rbp+hWndNewOwner]; hWndNewOwner
0x18006c40d  call    cs:__imp_OpenClipboard
0x18006c413  test    eax, eax
0x18006c415  jz      short loc_18006C48A
0x18006c417  call    cs:__imp_EmptyClipboard
0x18006c41d  test    eax, eax
0x18006c41f  jz      short loc_18006C48A
0x18006c421  movzx   ecx, word ptr cs:xmmword_1800A30F0; uFormat
0x18006c428  xor     edx, edx; hMem
0x18006c42a  call    cs:__imp_SetClipboardData
0x18006c430  xor     edx, edx; hMem
0x18006c432  lea     ecx, [rdx+0Dh]; uFormat
0x18006c435  call    cs:__imp_SetClipboardData
0x18006c43b  mov     rax, [rsi]
0x18006c43e  test    dword ptr [rax+0C0h], 0FF8FFEFFh
0x18006c448  jz      short loc_18006C468
0x18006c44a  movzx   ecx, word ptr cs:?g_rgFETC@@3PAUtagFORMATETC@@A; uFormat
0x18006c451  xor     edx, edx; hMem
0x18006c453  call    cs:__imp_SetClipboardData
0x18006c459  movzx   ecx, word ptr cs:xmmword_1800A3110; uFormat
0x18006c460  xor     edx, edx; hMem
0x18006c462  call    cs:__imp_SetClipboardData
0x18006c468  xor     edx, edx; hMem
0x18006c46a  lea     ecx, [rdx+1]; uFormat
0x18006c46d  call    cs:__imp_SetClipboardData
0x18006c473  test    edi, edi
0x18006c475  jz      short loc_18006C482
0x18006c477  xor     edx, edx; hMem
0x18006c479  lea     ecx, [rdx+8]; uFormat
0x18006c47c  call    cs:__imp_SetClipboardData
0x18006c482  call    cs:__imp_CloseClipboard
0x18006c488  xor     ebx, ebx
0x18006c48a  mov     rcx, [rsi+10h]
0x18006c48e  test    rcx, rcx
0x18006c491  jz      short loc_18006C49F
0x18006c493  mov     rax, [rcx]
0x18006c496  mov     rax, [rax+10h]
0x18006c49a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c49f  mov     rax, [rbp+arg_10]
0x18006c4a3  mov     [rsi+10h], rax
0x18006c4a7  mov     eax, ebx
0x18006c4a9  add     rsp, 30h
0x18006c4ad  pop     r15
0x18006c4af  pop     r14
0x18006c4b1  pop     r12
0x18006c4b3  pop     rdi
0x18006c4b4  pop     rsi
0x18006c4b5  pop     rbx
0x18006c4b6  pop     rbp
0x18006c4b7  retn
```
