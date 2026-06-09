# ATL::CWindowImplBaseT<ATL::CWindow,ATL::CWinTraits<1442840576,0>>::Create(HWND__ *,ATL::_U_RECT,ushort const *,ulong,ulong,ATL::_U_MENUorID,ushort,void *)

- ea: `0x1800075d8`
- end: `0x18000771f`
- name: `?Create@?$CWindowImplBaseT@VCWindow@ATL@@V?$CWinTraits@$0FGAAAAAA@$0A@@2@@ATL@@QEAAPEAUHWND__@@PEAU3@V_U_RECT@2@PEBGKKV_U_MENUorID@2@GPEAX@Z`
- size: `327`
- prototype: `HWND __fastcall(HMENU, HWND, int *, const WCHAR *, DWORD dwStyle, DWORD dwExStyle, HMENU, unsigned __int16)`
- caller_count: `6`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180007064`
- `0x18000dcc0`
- `0x18000dd60`
- `0x1800210e4`
- `0x180023660`
- `0x18002c798`

## callees

- `0x180006e00`
- `0x1800075d8`
- `0x18002d408`
- `0x18002d524`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180007666`
- `KERNEL32!EnterCriticalSection` at `0x180007666`
- `KERNEL32!LeaveCriticalSection` at `0x180007685`
- `KERNEL32!LeaveCriticalSection` at `0x180007685`
- `KERNEL32!GetCurrentThreadId` at `0x180007656`
- `KERNEL32!GetCurrentThreadId` at `0x180007656`
- `KERNEL32!SetLastError` at `0x18000760f`
- `KERNEL32!SetLastError` at `0x18000760f`
- `USER32!CreateWindowExW` at `0x180007709`
- `USER32!CreateWindowExW` at `0x180007709`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
HWND __fastcall ATL::CWindowImplBaseT<ATL::CWindow,ATL::CWinTraits<1442840576,0>>::Create(
        HMENU a1,
        HWND a2,
        int *a3,
        const WCHAR *a4,
        DWORD dwStyle,
        DWORD dwExStyle,
        HMENU a7,
        unsigned __int16 a8)
{
  AtlThunkData_t *Data; // rax
  int v14; // edx
  unsigned int v15; // r8d
  HMENU hMenu; // rcx
  int *v17; // rax

  Data = (AtlThunkData_t *)*((_QWORD *)a1 + 5);
  if ( !Data )
  {
    Data = AtlThunk_AllocateData();
    *((_QWORD *)a1 + 5) = Data;
    if ( !Data )
    {
      SetLastError(0xEu);
      return 0;
    }
  }
  AtlThunk_InitData(Data, 0, 0);
  if ( !a8 )
    return 0;
  if ( a1 == (HMENU)-16LL || !a1 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0xC0000005LL, v14, v15);
    JUMPOUT(0x18000771ELL);
  }
  *((_QWORD *)a1 + 2) = a1;
  *((_DWORD *)a1 + 6) = GetCurrentThreadId();
  EnterCriticalSection(&stru_1800503B8);
  *((_QWORD *)a1 + 4) = qword_1800503E0;
  qword_1800503E0 = (__int64)(a1 + 4);
  LeaveCriticalSection(&stru_1800503B8);
  hMenu = a7;
  if ( !a7 && (dwStyle & 0x40000000) != 0 )
    hMenu = a1;
  v17 = &ATL::CWindow::rcDefault;
  if ( a3 )
    v17 = a3;
  return CreateWindowExW(
           dwExStyle,
           (LPCWSTR)a8,
           a4,
           dwStyle,
           *v17,
           v17[1],
           v17[2] - *v17,
           v17[3] - v17[1],
           a2,
           hMenu,
           hInst,
           0);
}

```

## disassembly

```asm
0x1800075d8  push    rbx
0x1800075da  push    rsi
0x1800075db  push    rdi
0x1800075dc  push    r12
0x1800075de  push    r14
0x1800075e0  push    r15
0x1800075e2  sub     rsp, 68h
0x1800075e6  mov     rax, [rcx+28h]
0x1800075ea  xor     r12d, r12d
0x1800075ed  mov     r14, r9
0x1800075f0  mov     rbx, r8
0x1800075f3  mov     r15, rdx
0x1800075f6  mov     rdi, rcx
0x1800075f9  test    rax, rax
0x1800075fc  jnz     short loc_180007625
0x1800075fe  call    AtlThunk_AllocateData
0x180007603  mov     [rdi+28h], rax
0x180007607  test    rax, rax
0x18000760a  jnz     short loc_180007625
0x18000760c  lea     ecx, [rax+0Eh]; dwErrCode
0x18000760f  call    cs:__imp_SetLastError
0x180007615  xor     eax, eax
0x180007617  add     rsp, 68h
0x18000761b  pop     r15
0x18000761d  pop     r14
0x18000761f  pop     r12
0x180007621  pop     rdi
0x180007622  pop     rsi
0x180007623  pop     rbx
0x180007624  retn
0x180007625  xor     r8d, r8d; FirstParameter
0x180007628  xor     edx, edx; Proc
0x18000762a  mov     rcx, rax; Thunk
0x18000762d  call    AtlThunk_InitData
0x180007632  cmp     [rsp+98h+arg_38], r12w
0x18000763b  jz      short loc_180007615
0x18000763d  lea     rsi, [rdi+10h]
0x180007641  test    rsi, rsi
0x180007644  jz      loc_180007714
0x18000764a  test    rdi, rdi
0x18000764d  jz      loc_180007714
0x180007653  mov     [rsi], rdi
0x180007656  call    cs:__imp_GetCurrentThreadId
0x18000765c  lea     rcx, stru_1800503B8; lpCriticalSection
0x180007663  mov     [rsi+8], eax
0x180007666  call    cs:__imp_EnterCriticalSection
0x18000766c  mov     rax, cs:qword_1800503E0
0x180007673  lea     rcx, stru_1800503B8; lpCriticalSection
0x18000767a  mov     [rsi+10h], rax
0x18000767e  mov     cs:qword_1800503E0, rsi
0x180007685  call    cs:__imp_LeaveCriticalSection
0x18000768b  mov     rcx, [rsp+98h+arg_30]
0x180007693  mov     r9d, [rsp+98h+dwStyle]; dwStyle
0x18000769b  test    rcx, rcx
0x18000769e  jnz     short loc_1800076A9
0x1800076a0  bt      r9d, 1Eh
0x1800076a5  cmovb   rcx, rdi
0x1800076a9  mov     r10, cs:hInst
0x1800076b0  lea     rax, ?rcDefault@CWindow@ATL@@2UtagRECT@@A; tagRECT ATL::CWindow::rcDefault
0x1800076b7  movzx   edx, [rsp+98h+arg_38]; lpClassName
0x1800076bf  test    rbx, rbx
0x1800076c2  mov     [rsp+98h+lpParam], r12; lpParam
0x1800076c7  cmovnz  rax, rbx
0x1800076cb  mov     [rsp+98h+hInstance], r10; hInstance
0x1800076d0  mov     [rsp+98h+hMenu], rcx; hMenu
0x1800076d5  mov     ecx, [rsp+98h+dwExStyle]; dwExStyle
0x1800076dc  mov     [rsp+98h+hWndParent], r15; hWndParent
0x1800076e1  mov     ebx, [rax+4]
0x1800076e4  mov     r8d, [rax+8]
0x1800076e8  mov     edi, [rax]
0x1800076ea  sub     r8d, edi
0x1800076ed  mov     r11d, [rax+0Ch]
0x1800076f1  sub     r11d, ebx
0x1800076f4  mov     [rsp+98h+nHeight], r11d; nHeight
0x1800076f9  mov     [rsp+98h+nWidth], r8d; nWidth
0x1800076fe  mov     r8, r14; lpWindowName
0x180007701  mov     [rsp+98h+Y], ebx; Y
0x180007705  mov     [rsp+98h+X], edi; X
0x180007709  call    cs:__imp_CreateWindowExW
0x18000770f  jmp     loc_180007617
0x180007714  mov     ecx, 0C0000005h; this
0x180007719  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
