# CLightDTEngine::CopyRangeToClipboard(CTxtRange *,long,int)

- ea: `0x1801627ec`
- end: `0x180162a5f`
- name: `?CopyRangeToClipboard@CLightDTEngine@@QEAAJPEAVCTxtRange@@JH@Z`
- size: `627`
- prototype: `__int64 __fastcall(CLightDTEngine *__hidden this, struct CTxtRange *, int, int)`
- caller_count: `3`
- callee_count: `9`
- tags: ``

## callers

- `0x180128354`
- `0x180162c84`
- `0x180176b6c`

## callees

- `0x180090884`
- `0x180091f84`
- `0x1800d9184`
- `0x1800f7d74`
- `0x180100c98`
- `0x1801627ec`
- `0x180163d60`
- `0x1801643b4`
- `0x18027a010`

## import_xrefs

- `ext-ms-win-ntuser-misc-l1-2-0!CloseClipboard` at `0x1801629d1`
- `ext-ms-win-ntuser-misc-l1-2-0!CloseClipboard` at `0x1801629d1`
- `ext-ms-win-ntuser-misc-l1-2-0!OpenClipboard` at `0x180162958`
- `ext-ms-win-ntuser-misc-l1-2-0!OpenClipboard` at `0x180162958`
- `ext-ms-win-ntuser-misc-l1-2-0!SetClipboardData` at `0x180162971`
- `ext-ms-win-ntuser-misc-l1-2-0!SetClipboardData` at `0x180162980`
- `ext-ms-win-ntuser-misc-l1-2-0!SetClipboardData` at `0x1801629a2`
- `ext-ms-win-ntuser-misc-l1-2-0!SetClipboardData` at `0x1801629b1`
- `ext-ms-win-ntuser-misc-l1-2-0!SetClipboardData` at `0x1801629bc`
- `ext-ms-win-ntuser-misc-l1-2-0!SetClipboardData` at `0x1801629cb`
- `ext-ms-win-ntuser-misc-l1-2-0!SetClipboardData` at `0x180162971`
- `ext-ms-win-ntuser-misc-l1-2-0!SetClipboardData` at `0x180162980`
- `ext-ms-win-ntuser-misc-l1-2-0!SetClipboardData` at `0x1801629a2`
- `ext-ms-win-ntuser-misc-l1-2-0!SetClipboardData` at `0x1801629b1`
- `ext-ms-win-ntuser-misc-l1-2-0!SetClipboardData` at `0x1801629bc`
- `ext-ms-win-ntuser-misc-l1-2-0!SetClipboardData` at `0x1801629cb`
- `ext-ms-win-ntuser-misc-l1-2-0!EmptyClipboard` at `0x180162962`
- `ext-ms-win-ntuser-misc-l1-2-0!EmptyClipboard` at `0x180162962`

## pseudocode

```c
__int64 __fastcall CLightDTEngine::CopyRangeToClipboard(CTxtEdit **this, struct CTxtRange *a2, int a3, int a4)
{
  CTxtEdit *v4; // rax
  _QWORD *v9; // r15
  __int64 v11; // rax
  struct CTxtStory *v12; // rdi
  int IndexForCp; // ebx
  CObjectMgr *v14; // rcx
  BOOL v15; // edi
  unsigned int v16; // ebx
  char v17; // r15
  CTxtEdit *v18; // rcx
  CTxtEdit *v19; // rcx
  HWND hWndNewOwner; // [rsp+30h] [rbp-18h] BYREF
  struct IDataObject *v21[2]; // [rsp+38h] [rbp-10h] BYREF
  __int64 v22; // [rsp+90h] [rbp+48h] BYREF

  v4 = *this;
  v22 = 0;
  v21[0] = 0;
  v9 = (_QWORD *)*((_QWORD *)v4 + 30);
  if ( v9 )
    v9 = (_QWORD *)v9[3];
  CTxtRange::GetRange(a2, (int *)&v22, (int *)&v22 + 1);
  if ( (int)v22 >= SHIDWORD(v22) )
    return 0;
  v15 = 0;
  if ( HIDWORD(v22) - (_DWORD)v22 == 1 )
  {
    if ( (unsigned int)CRchTxtPtr::GetObjectCount((struct CTxtRange *)((char *)a2 + 8)) )
    {
      v11 = *((_QWORD *)a2 + 3);
      v12 = (struct CTxtStory *)((v11 - 8) & -(__int64)(v11 != 0));
      IndexForCp = CObjectMgr::FindIndexForCp((CObjectMgr *)(v11 - 8), SHIDWORD(v22), v12);
      if ( IndexForCp != CObjectMgr::FindIndexForCp(v14, v22, v12) )
        v15 = 1;
    }
  }
  if ( !v9
    || (v16 = (*(__int64 (__fastcall **)(_QWORD *, __int64 *, _QWORD, struct IDataObject **))(*v9 + 80LL))(
                v9,
                &v22,
                (unsigned int)(a4 != 0) + 2,
                v21)) != 0 )
  {
    if ( !*((_DWORD *)a2 + 26) )
    {
      CTxtEdit::Beep(*this);
      return 0;
    }
    v17 = 0;
    v16 = CLightDTEngine::RangeToDataObject((CLightDTEngine *)this, a2, a3 | 3, v21);
    if ( v16 )
      return v16;
  }
  else
  {
    v17 = 1;
  }
  if ( v21[0] )
  {
    v16 = (*(__int64 (__fastcall **)(struct IClipboard *, struct IDataObject *, CTxtEdit *))(*(_QWORD *)g_pIClipboard
                                                                                           + 24LL))(
            g_pIClipboard,
            v21[0],
            this[4]);
    if ( v16 )
    {
      v18 = *this;
      hWndNewOwner = 0;
      *((_BYTE *)this + 26) = 1;
      if ( !(unsigned int)CTxtEdit::TxGetWindow(v18, &hWndNewOwner) && OpenClipboard(hWndNewOwner) && EmptyClipboard() )
      {
        SetClipboardData(0xDu, 0);
        SetClipboardData(stru_1802DC9E0.cfFormat, 0);
        if ( (*((_QWORD *)*this + 12) & 0xFFFFFFFFFFFBFE3FuLL) != 0 || *((_QWORD *)*this + 13) )
        {
          SetClipboardData(stru_1802DC9C0.cfFormat, 0);
          SetClipboardData(stru_1802DCA00.cfFormat, 0);
        }
        SetClipboardData(1u, 0);
        if ( v15 )
          SetClipboardData(8u, 0);
        CloseClipboard();
        v16 = 0;
      }
    }
    v19 = this[2];
    if ( !v19 )
      goto LABEL_35;
    hWndNewOwner = 0;
    if ( (**(unsigned int (__fastcall ***)(CTxtEdit *, GUID *, HWND *))v19)(v19, &IID_IRichEditDO, &hWndNewOwner) )
      hWndNewOwner = 0;
    if ( CLightDTEngine::ReleaseDataObject((CLightDTEngine *)this) > 1 )
    {
      if ( !hWndNewOwner )
      {
LABEL_35:
        this[2] = (CTxtEdit *)v21[0];
        *((_BYTE *)this + 24) = v17;
        return v16;
      }
      (*(void (__fastcall **)(HWND))(*((_QWORD *)hWndNewOwner + 1) + 16LL))(hWndNewOwner + 2);
    }
    if ( hWndNewOwner )
      (*(void (__fastcall **)(HWND))(*(_QWORD *)hWndNewOwner + 16LL))(hWndNewOwner);
    goto LABEL_35;
  }
  return v16;
}

```

## disassembly

```asm
0x1801627ec  push    rbp
0x1801627ee  push    rbx
0x1801627ef  push    rsi
0x1801627f0  push    rdi
0x1801627f1  push    r12
0x1801627f3  push    r13
0x1801627f5  push    r14
0x1801627f7  push    r15
0x1801627f9  mov     rbp, rsp
0x1801627fc  sub     rsp, 48h
0x180162800  mov     rax, [rcx]
0x180162803  mov     r13d, r9d
0x180162806  mov     qword ptr [rbp+arg_0], 0
0x18016280e  mov     r12d, r8d
0x180162811  mov     [rbp+var_10], 0
0x180162819  mov     r14, rdx
0x18016281c  mov     rsi, rcx
0x18016281f  mov     r15, [rax+0F0h]
0x180162826  test    r15, r15
0x180162829  jz      short loc_18016282F
0x18016282b  mov     r15, [r15+18h]
0x18016282f  lea     r8, [rbp+arg_4]; int *
0x180162833  mov     rcx, r14; this
0x180162836  lea     rdx, [rbp+arg_0]; int *
0x18016283a  call    ?GetRange@CTxtRange@@QEBAJAEAJ0@Z; CTxtRange::GetRange(long &,long &)
0x18016283f  mov     eax, [rbp+arg_4]
0x180162842  cmp     [rbp+arg_0], eax
0x180162845  jl      short loc_18016284E
0x180162847  xor     eax, eax
0x180162849  jmp     loc_180162A4E
0x18016284e  sub     eax, [rbp+arg_0]
0x180162851  cmp     eax, 1
0x180162854  jnz     short loc_180162897
0x180162856  lea     rcx, [r14+8]; this
0x18016285a  call    ?GetObjectCount@CRchTxtPtr@@QEBAJXZ; CRchTxtPtr::GetObjectCount(void)
0x18016285f  test    eax, eax
0x180162861  jz      short loc_180162897
0x180162863  mov     rax, [r14+18h]
0x180162867  mov     edx, [rbp+arg_4]; int
0x18016286a  lea     rcx, [rax-8]; this
0x18016286e  neg     rax
0x180162871  sbb     rdi, rdi
0x180162874  and     rdi, rcx
0x180162877  mov     r8, rdi; struct CTxtStory *
0x18016287a  call    ?FindIndexForCp@CObjectMgr@@QEAAJJPEAVCTxtStory@@@Z; CObjectMgr::FindIndexForCp(long,CTxtStory *)
0x18016287f  mov     edx, [rbp+arg_0]; int
0x180162882  mov     r8, rdi; struct CTxtStory *
0x180162885  mov     ebx, eax
0x180162887  call    ?FindIndexForCp@CObjectMgr@@QEAAJJPEAVCTxtStory@@@Z; CObjectMgr::FindIndexForCp(long,CTxtStory *)
0x18016288c  cmp     ebx, eax
0x18016288e  jz      short loc_180162897
0x180162890  mov     edi, 1
0x180162895  jmp     short loc_180162899
0x180162897  xor     edi, edi
0x180162899  test    r15, r15
0x18016289c  jz      short loc_1801628D1
0x18016289e  mov     rax, [r15]
0x1801628a1  lea     r9, [rbp+var_10]
0x1801628a5  neg     r13d
0x1801628a8  lea     rdx, [rbp+arg_0]
0x1801628ac  mov     rcx, r15
0x1801628af  sbb     r8d, r8d
0x1801628b2  mov     rax, [rax+50h]
0x1801628b6  neg     r8d
0x1801628b9  add     r8d, 2
0x1801628bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801628c2  xor     r13d, r13d
0x1801628c5  mov     ebx, eax
0x1801628c7  test    eax, eax
0x1801628c9  jnz     short loc_1801628D4
0x1801628cb  lea     r15d, [rax+1]
0x1801628cf  jmp     short loc_18016290A
0x1801628d1  xor     r13d, r13d
0x1801628d4  cmp     [r14+68h], r13d
0x1801628d8  jnz     short loc_1801628E7
0x1801628da  mov     rcx, [rsi]; this
0x1801628dd  call    ?Beep@CTxtEdit@@QEAAXXZ; CTxtEdit::Beep(void)
0x1801628e2  jmp     loc_180162847
0x1801628e7  or      r12d, 3
0x1801628eb  lea     r9, [rbp+var_10]; struct IDataObject **
0x1801628ef  mov     r8d, r12d; int
0x1801628f2  mov     rdx, r14; struct CTxtRange *
0x1801628f5  mov     rcx, rsi; this
0x1801628f8  mov     r15d, r13d
0x1801628fb  call    ?RangeToDataObject@CLightDTEngine@@QEAAJPEAVCTxtRange@@JPEAPEAUIDataObject@@@Z; CLightDTEngine::RangeToDataObject(CTxtRange *,long,IDataObject * *)
0x180162900  mov     ebx, eax
0x180162902  test    eax, eax
0x180162904  jnz     loc_180162A4C
0x18016290a  mov     rdx, [rbp+var_10]
0x18016290e  test    rdx, rdx
0x180162911  jz      loc_180162A4C
0x180162917  mov     rcx, cs:?g_pIClipboard@@3PEAVIClipboard@@EA; IClipboard * g_pIClipboard
0x18016291e  mov     r8, [rsi+20h]
0x180162922  mov     rax, [rcx]
0x180162925  mov     rax, [rax+18h]
0x180162929  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016292e  mov     ebx, eax
0x180162930  test    eax, eax
0x180162932  jz      loc_1801629DA
0x180162938  mov     rcx, [rsi]; this
0x18016293b  lea     rdx, [rbp+hWndNewOwner]; HWND *
0x18016293f  mov     [rbp+hWndNewOwner], r13
0x180162943  mov     byte ptr [rsi+1Ah], 1
0x180162947  call    ?TxGetWindow@CTxtEdit@@QEAAJPEAPEAUHWND__@@@Z; CTxtEdit::TxGetWindow(HWND__ * *)
0x18016294c  test    eax, eax
0x18016294e  jnz     loc_1801629DA
0x180162954  mov     rcx, [rbp+hWndNewOwner]; hWndNewOwner
0x180162958  call    cs:__imp_OpenClipboard
0x18016295e  test    eax, eax
0x180162960  jz      short loc_1801629DA
0x180162962  call    cs:__imp_EmptyClipboard
0x180162968  test    eax, eax
0x18016296a  jz      short loc_1801629DA
0x18016296c  xor     edx, edx; hMem
0x18016296e  lea     ecx, [rdx+0Dh]; uFormat
0x180162971  call    cs:__imp_SetClipboardData
0x180162977  movzx   ecx, cs:stru_1802DC9E0.cfFormat; uFormat
0x18016297e  xor     edx, edx; hMem
0x180162980  call    cs:__imp_SetClipboardData
0x180162986  mov     rax, [rsi]
0x180162989  test    qword ptr [rax+60h], 0FFFFFFFFFFFBFE3Fh
0x180162991  jnz     short loc_180162999
0x180162993  cmp     [rax+68h], r13
0x180162997  jz      short loc_1801629B7
0x180162999  movzx   ecx, cs:stru_1802DC9C0.cfFormat; uFormat
0x1801629a0  xor     edx, edx; hMem
0x1801629a2  call    cs:__imp_SetClipboardData
0x1801629a8  movzx   ecx, cs:stru_1802DCA00.cfFormat; uFormat
0x1801629af  xor     edx, edx; hMem
0x1801629b1  call    cs:__imp_SetClipboardData
0x1801629b7  xor     edx, edx; hMem
0x1801629b9  lea     ecx, [rdx+1]; uFormat
0x1801629bc  call    cs:__imp_SetClipboardData
0x1801629c2  test    edi, edi
0x1801629c4  jz      short loc_1801629D1
0x1801629c6  xor     edx, edx; hMem
0x1801629c8  lea     ecx, [rdx+8]; uFormat
0x1801629cb  call    cs:__imp_SetClipboardData
0x1801629d1  call    cs:__imp_CloseClipboard
0x1801629d7  mov     ebx, r13d
0x1801629da  mov     rcx, [rsi+10h]
0x1801629de  test    rcx, rcx
0x1801629e1  jz      short loc_180162A40
0x1801629e3  mov     [rbp+hWndNewOwner], r13
0x1801629e7  lea     r8, [rbp+hWndNewOwner]
0x1801629eb  mov     rax, [rcx]
0x1801629ee  lea     rdx, IID_IRichEditDO
0x1801629f5  mov     rax, [rax]
0x1801629f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801629fd  test    eax, eax
0x1801629ff  jz      short loc_180162A05
0x180162a01  mov     [rbp+hWndNewOwner], r13
0x180162a05  mov     rcx, rsi; this
0x180162a08  call    ?ReleaseDataObject@CLightDTEngine@@AEAAKXZ; CLightDTEngine::ReleaseDataObject(void)
0x180162a0d  cmp     eax, 1
0x180162a10  jbe     short loc_180162A2B
0x180162a12  mov     rcx, [rbp+hWndNewOwner]
0x180162a16  test    rcx, rcx
0x180162a19  jz      short loc_180162A40
0x180162a1b  add     rcx, 8
0x180162a1f  mov     rax, [rcx]
0x180162a22  mov     rax, [rax+10h]
0x180162a26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180162a2b  mov     rcx, [rbp+hWndNewOwner]
0x180162a2f  test    rcx, rcx
0x180162a32  jz      short loc_180162A40
0x180162a34  mov     rax, [rcx]
0x180162a37  mov     rax, [rax+10h]
0x180162a3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180162a40  mov     rax, [rbp+var_10]
0x180162a44  mov     [rsi+10h], rax
0x180162a48  mov     [rsi+18h], r15b
0x180162a4c  mov     eax, ebx
0x180162a4e  add     rsp, 48h
0x180162a52  pop     r15
0x180162a54  pop     r14
0x180162a56  pop     r13
0x180162a58  pop     r12
0x180162a5a  pop     rdi
0x180162a5b  pop     rsi
0x180162a5c  pop     rbx
0x180162a5d  pop     rbp
0x180162a5e  retn
```
