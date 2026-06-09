# ATL::CDialogImplBaseT<ATL::CWindow>::StartDialogProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x180009600`
- end: `0x1800096f7`
- name: `?StartDialogProc@?$CDialogImplBaseT@VCWindow@ATL@@@ATL@@SA_JPEAUHWND__@@I_K_J@Z`
- size: `247`
- prototype: `__int64 __fastcall(HWND hWnd)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180009600`
- `0x18000a6f8`
- `0x18000a770`
- `0x18000a814`
- `0x18000c010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180009634`
- `KERNEL32!GetCurrentThreadId` at `0x180009634`
- `KERNEL32!EnterCriticalSection` at `0x180009620`
- `KERNEL32!EnterCriticalSection` at `0x180009620`
- `KERNEL32!LeaveCriticalSection` at `0x18000966f`
- `KERNEL32!LeaveCriticalSection` at `0x18000966f`
- `USER32!SetWindowLongPtrW` at `0x1800096d0`
- `USER32!SetWindowLongPtrW` at `0x1800096d0`

## pseudocode

```c
__int64 __fastcall ATL::CDialogImplBaseT<ATL::CWindow>::StartDialogProc(
        HWND hWnd,
        unsigned int a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v8; // rdi
  size_t v9; // rbx
  DWORD CurrentThreadId; // eax
  __int64 v11; // r8
  __int64 v12; // rcx
  __int64 v14; // rax
  void *v15; // rdi
  AtlThunkData_t *Data; // rax
  WNDPROC v17; // rbx

  EnterCriticalSection(&stru_180013368);
  v8 = qword_180013390;
  v9 = 0;
  if ( qword_180013390 )
  {
    CurrentThreadId = GetCurrentThreadId();
    v11 = 0;
    while ( 1 )
    {
      v12 = *(_QWORD *)(v8 + 16);
      if ( *(_DWORD *)(v8 + 8) == CurrentThreadId )
        break;
      v11 = v8;
      v8 = *(_QWORD *)(v8 + 16);
      if ( !v12 )
        goto LABEL_10;
    }
    if ( v11 )
      *(_QWORD *)(v11 + 16) = v12;
    else
      qword_180013390 = *(_QWORD *)(v8 + 16);
    v9 = *(_QWORD *)v8;
  }
LABEL_10:
  LeaveCriticalSection(&stru_180013368);
  if ( !v9 )
    return 0;
  v14 = *(_QWORD *)v9;
  *(_QWORD *)(v9 + 8) = hWnd;
  v15 = (void *)(*(__int64 (__fastcall **)(size_t))(v14 + 16))(v9);
  Data = *(AtlThunkData_t **)(v9 + 40);
  if ( Data || (Data = AtlThunk_AllocateData(), (*(_QWORD *)(v9 + 40) = Data) != 0) )
    AtlThunk_InitData(Data, v15, v9);
  v17 = AtlThunk_DataToCode(*(AtlThunkData_t **)(v9 + 40));
  SetWindowLongPtrW(hWnd, 8, (LONG_PTR)v17);
  return ((__int64 (__fastcall *)(HWND, _QWORD, __int64, __int64))v17)(hWnd, a2, a3, a4);
}

```

## disassembly

```asm
0x180009600  push    rbx
0x180009602  push    rbp
0x180009603  push    rsi
0x180009604  push    rdi
0x180009605  push    r14
0x180009607  push    r15
0x180009609  sub     rsp, 38h
0x18000960d  mov     rsi, rcx
0x180009610  mov     rbp, r9
0x180009613  lea     rcx, stru_180013368; lpCriticalSection
0x18000961a  mov     r14, r8
0x18000961d  mov     r15d, edx
0x180009620  call    cs:__imp_EnterCriticalSection
0x180009626  mov     rdi, cs:qword_180013390
0x18000962d  xor     ebx, ebx
0x18000962f  test    rdi, rdi
0x180009632  jz      short loc_180009668
0x180009634  call    cs:__imp_GetCurrentThreadId
0x18000963a  xor     r8d, r8d
0x18000963d  mov     rcx, [rdi+10h]
0x180009641  cmp     [rdi+8], eax
0x180009644  jz      short loc_180009653
0x180009646  mov     r8, rdi
0x180009649  mov     rdi, rcx
0x18000964c  test    rcx, rcx
0x18000964f  jnz     short loc_18000963D
0x180009651  jmp     short loc_180009668
0x180009653  test    r8, r8
0x180009656  jnz     short loc_180009661
0x180009658  mov     cs:qword_180013390, rcx
0x18000965f  jmp     short loc_180009665
0x180009661  mov     [r8+10h], rcx
0x180009665  mov     rbx, [rdi]
0x180009668  lea     rcx, stru_180013368; lpCriticalSection
0x18000966f  call    cs:__imp_LeaveCriticalSection
0x180009675  test    rbx, rbx
0x180009678  jnz     short loc_18000967E
0x18000967a  xor     eax, eax
0x18000967c  jmp     short loc_1800096EA
0x18000967e  mov     rax, [rbx]
0x180009681  mov     rcx, rbx
0x180009684  mov     [rbx+8], rsi
0x180009688  mov     rax, [rax+10h]
0x18000968c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009691  mov     rdi, rax
0x180009694  mov     rax, [rbx+28h]
0x180009698  test    rax, rax
0x18000969b  jnz     short loc_1800096AB
0x18000969d  call    AtlThunk_AllocateData
0x1800096a2  mov     [rbx+28h], rax
0x1800096a6  test    rax, rax
0x1800096a9  jz      short loc_1800096B9
0x1800096ab  mov     r8, rbx; FirstParameter
0x1800096ae  mov     rdx, rdi; Proc
0x1800096b1  mov     rcx, rax; Thunk
0x1800096b4  call    AtlThunk_InitData
0x1800096b9  mov     rcx, [rbx+28h]; AtlThunkData_t *
0x1800096bd  call    AtlThunk_DataToCode
0x1800096c2  mov     r8, rax; dwNewLong
0x1800096c5  mov     edx, 8; nIndex
0x1800096ca  mov     rcx, rsi; hWnd
0x1800096cd  mov     rbx, rax
0x1800096d0  call    cs:__imp_SetWindowLongPtrW
0x1800096d6  mov     r9, rbp
0x1800096d9  mov     r8, r14
0x1800096dc  mov     edx, r15d
0x1800096df  mov     rcx, rsi
0x1800096e2  mov     rax, rbx
0x1800096e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800096ea  add     rsp, 38h
0x1800096ee  pop     r15
0x1800096f0  pop     r14
0x1800096f2  pop     rdi
0x1800096f3  pop     rsi
0x1800096f4  pop     rbp
0x1800096f5  pop     rbx
0x1800096f6  retn
```
