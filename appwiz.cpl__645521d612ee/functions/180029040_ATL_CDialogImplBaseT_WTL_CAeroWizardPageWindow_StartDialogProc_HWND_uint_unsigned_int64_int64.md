# ATL::CDialogImplBaseT<WTL::CAeroWizardPageWindow>::StartDialogProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x180029040`
- end: `0x180029151`
- name: `?StartDialogProc@?$CDialogImplBaseT@VCAeroWizardPageWindow@WTL@@@ATL@@SA_JPEAUHWND__@@I_K_J@Z`
- size: `273`
- prototype: `__int64 __fastcall(HWND hWnd)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180024038`
- `0x180026538`
- `0x180029040`
- `0x180050ae0`
- `0x180050b58`
- `0x180050bf4`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180029092`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180029092`
- `USER32!SetWindowLongPtrW` at `0x18002912a`
- `USER32!SetWindowLongPtrW` at `0x18002912a`

## pseudocode

```c
__int64 __fastcall ATL::CDialogImplBaseT<WTL::CAeroWizardPageWindow>::StartDialogProc(
        HWND hWnd,
        unsigned int a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v8; // rbx
  size_t v9; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v11; // rdx
  __int64 v13; // rax
  void *v14; // rbx
  AtlThunkData_t *Data; // rax
  WNDPROC v16; // rbx
  __int64 *v17; // [rsp+30h] [rbp-48h] BYREF
  char v18; // [rsp+38h] [rbp-40h]

  v18 = 0;
  v17 = qword_180078238;
  if ( (int)ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(&v17) < 0 )
  {
    ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(&v17);
    return 0;
  }
  v8 = qword_180078260;
  v9 = 0;
  if ( qword_180078260 )
  {
    CurrentThreadId = GetCurrentThreadId();
    v11 = 0;
    while ( v8 )
    {
      if ( *(_DWORD *)(v8 + 8) == CurrentThreadId )
      {
        if ( v11 )
          *(_QWORD *)(v11 + 16) = *(_QWORD *)(v8 + 16);
        else
          qword_180078260 = *(_QWORD *)(v8 + 16);
        v9 = *(_QWORD *)v8;
        break;
      }
      v11 = v8;
      v8 = *(_QWORD *)(v8 + 16);
    }
  }
  ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(&v17);
  if ( !v9 )
    return 0;
  v13 = *(_QWORD *)v9;
  *(_QWORD *)(v9 + 8) = hWnd;
  v14 = (void *)(*(__int64 (__fastcall **)(size_t))(v13 + 16))(v9);
  Data = *(AtlThunkData_t **)(v9 + 40);
  if ( Data || (Data = AtlThunk_AllocateData(), (*(_QWORD *)(v9 + 40) = Data) != 0) )
    AtlThunk_InitData(Data, v14, v9);
  v16 = AtlThunk_DataToCode(*(AtlThunkData_t **)(v9 + 40));
  SetWindowLongPtrW(hWnd, 8, (LONG_PTR)v16);
  return ((__int64 (__fastcall *)(HWND, _QWORD, __int64, __int64))v16)(hWnd, a2, a3, a4);
}

```

## disassembly

```asm
0x180029040  push    rbx
0x180029042  push    rbp
0x180029043  push    rsi
0x180029044  push    rdi
0x180029045  push    r14
0x180029047  push    r15
0x180029049  sub     rsp, 48h
0x18002904d  mov     rsi, rcx
0x180029050  mov     [rsp+78h+var_40], 0
0x180029055  lea     rax, qword_180078238
0x18002905c  mov     rbp, r9
0x18002905f  lea     rcx, [rsp+78h+var_48]
0x180029064  mov     [rsp+78h+var_48], rax
0x180029069  mov     r14, r8
0x18002906c  mov     r15d, edx
0x18002906f  call    ?Lock@?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAAJXZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(void)
0x180029074  test    eax, eax
0x180029076  jns     short loc_180029084
0x180029078  lea     rcx, [rsp+78h+var_48]
0x18002907d  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x180029082  jmp     short loc_1800290D4
0x180029084  mov     rbx, cs:qword_180078260
0x18002908b  xor     edi, edi
0x18002908d  test    rbx, rbx
0x180029090  jz      short loc_1800290C5
0x180029092  call    cs:__imp_GetCurrentThreadId
0x180029098  xor     edx, edx
0x18002909a  test    rbx, rbx
0x18002909d  jz      short loc_1800290C5
0x18002909f  mov     rcx, [rbx+10h]
0x1800290a3  cmp     [rbx+8], eax
0x1800290a6  jz      short loc_1800290B0
0x1800290a8  mov     rdx, rbx
0x1800290ab  mov     rbx, rcx
0x1800290ae  jmp     short loc_18002909A
0x1800290b0  test    rdx, rdx
0x1800290b3  jnz     short loc_1800290BE
0x1800290b5  mov     cs:qword_180078260, rcx
0x1800290bc  jmp     short loc_1800290C2
0x1800290be  mov     [rdx+10h], rcx
0x1800290c2  mov     rdi, [rbx]
0x1800290c5  lea     rcx, [rsp+78h+var_48]
0x1800290ca  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x1800290cf  test    rdi, rdi
0x1800290d2  jnz     short loc_1800290D8
0x1800290d4  xor     eax, eax
0x1800290d6  jmp     short loc_180029144
0x1800290d8  mov     rax, [rdi]
0x1800290db  mov     rcx, rdi
0x1800290de  mov     [rdi+8], rsi
0x1800290e2  mov     rax, [rax+10h]
0x1800290e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800290eb  mov     rbx, rax
0x1800290ee  mov     rax, [rdi+28h]
0x1800290f2  test    rax, rax
0x1800290f5  jnz     short loc_180029105
0x1800290f7  call    AtlThunk_AllocateData
0x1800290fc  mov     [rdi+28h], rax
0x180029100  test    rax, rax
0x180029103  jz      short loc_180029113
0x180029105  mov     r8, rdi; FirstParameter
0x180029108  mov     rdx, rbx; Proc
0x18002910b  mov     rcx, rax; Thunk
0x18002910e  call    AtlThunk_InitData
0x180029113  mov     rcx, [rdi+28h]; AtlThunkData_t *
0x180029117  call    AtlThunk_DataToCode
0x18002911c  mov     r8, rax; dwNewLong
0x18002911f  mov     edx, 8; nIndex
0x180029124  mov     rcx, rsi; hWnd
0x180029127  mov     rbx, rax
0x18002912a  call    cs:__imp_SetWindowLongPtrW
0x180029130  mov     r9, rbp
0x180029133  mov     r8, r14
0x180029136  mov     edx, r15d
0x180029139  mov     rcx, rsi
0x18002913c  mov     rax, rbx
0x18002913f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029144  add     rsp, 48h
0x180029148  pop     r15
0x18002914a  pop     r14
0x18002914c  pop     rdi
0x18002914d  pop     rsi
0x18002914e  pop     rbp
0x18002914f  pop     rbx
0x180029150  retn
```
