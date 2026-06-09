# TaskbarList::ThumbBarSetImageList(HWND__ *,_IMAGELIST *)

- ea: `0x18008a600`
- end: `0x18008a771`
- name: `?ThumbBarSetImageList@TaskbarList@@UEAAJPEAUHWND__@@PEAU_IMAGELIST@@@Z`
- size: `369`
- prototype: `int(TaskbarList *__hidden this, HWND, struct _IMAGELIST *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, service_task`

## callees

- `0x1800899cc`
- `0x180089d70`
- `0x18008a600`
- `0x18008a884`
- `0x180210010`

## import_xrefs

- `SHCORE!SHCreateMemStream` at `0x18008a639`
- `SHCORE!SHCreateMemStream` at `0x18008a639`
- `SHCORE!IStream_Size` at `0x18008a66d`
- `SHCORE!IStream_Size` at `0x18008a66d`
- `SHCORE!IStream_Read` at `0x18008a6e1`
- `SHCORE!IStream_Read` at `0x18008a6e1`
- `SHCORE!IStream_Reset` at `0x18008a6d0`
- `SHCORE!IStream_Reset` at `0x18008a6d0`
- `SHCORE!__imp_SHAllocShared` at `0x18008a69b`
- `SHCORE!__imp_SHAllocShared` at `0x18008a69b`
- `SHCORE!__imp_SHLockSharedEx` at `0x18008a6b9`
- `SHCORE!__imp_SHLockSharedEx` at `0x18008a6b9`
- `SHCORE!__imp_SHUnlockShared` at `0x18008a6ea`
- `SHCORE!__imp_SHUnlockShared` at `0x18008a6ea`
- `SHCORE!__imp_SHFreeShared` at `0x18008a736`
- `SHCORE!__imp_SHFreeShared` at `0x18008a736`
- `USER32!SendMessageTimeoutW` at `0x18008a71f`
- `USER32!SendMessageTimeoutW` at `0x18008a71f`
- `USER32!GetWindowThreadProcessId` at `0x18008a689`
- `USER32!GetWindowThreadProcessId` at `0x18008a689`

## pseudocode

```c
__int64 __fastcall TaskbarList::ThumbBarSetImageList(TaskbarList *this, WPARAM a2, struct _IMAGELIST *a3)
{
  int v5; // edi
  HWND TaskbarList; // r14
  struct IStream *v7; // rax
  IStream *v8; // rbx
  HANDLE v9; // rax
  void *v10; // rsi
  DWORD *v11; // r15
  ULARGE_INTEGER pui; // [rsp+40h] [rbp-10h] BYREF
  ULONG_PTR dwResult; // [rsp+48h] [rbp-8h] BYREF
  DWORD dwProcessId; // [rsp+98h] [rbp+48h] BYREF

  v5 = -2147467259;
  TaskbarList = TaskbarList::_HwndGetTaskbarList(this);
  if ( TaskbarList )
  {
    v7 = SHCreateMemStream(0, 0);
    v8 = v7;
    if ( !v7 )
      return (unsigned int)ResultFromKnownLastError();
    if ( ImageList_Write(a3, v7) )
    {
      pui.QuadPart = 0;
      if ( IStream_Size(v8, &pui) >= 0 )
      {
        dwProcessId = 0;
        GetWindowThreadProcessId(TaskbarList, &dwProcessId);
        v9 = SHAllocShared(0, pui.LowPart + 4, dwProcessId);
        v10 = v9;
        if ( v9 )
        {
          v11 = (DWORD *)SHLockSharedEx(v9, dwProcessId, 1);
          if ( v11 )
          {
            *v11 = pui.LowPart;
            IStream_Reset(v8);
            IStream_Read(v8, v11 + 1, pui.LowPart);
            SHUnlockShared(v11);
            dwResult = 0;
            if ( SendMessageTimeoutW(TaskbarList, 0x44Eu, a2, (LPARAM)v10, 2u, 0xBB8u, &dwResult) )
              v5 = 0;
          }
          SHFreeShared(v10, dwProcessId);
        }
      }
    }
    (*(void (__fastcall **)(IStream *))(*(_QWORD *)v8 + 16LL))(v8);
    if ( v5 < 0 )
      return (unsigned int)ResultFromKnownLastError();
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18008a600  mov     [rsp-28h+arg_0], rbx
0x18008a605  mov     [rsp-28h+arg_8], rsi
0x18008a60a  push    rbp
0x18008a60b  push    rdi
0x18008a60c  push    r12
0x18008a60e  push    r14
0x18008a610  push    r15
0x18008a612  mov     rbp, rsp
0x18008a615  sub     rsp, 50h
0x18008a619  mov     rsi, r8
0x18008a61c  mov     r12, rdx
0x18008a61f  mov     edi, 80004005h
0x18008a624  call    ?_HwndGetTaskbarList@TaskbarList@@IEAAPEAUHWND__@@XZ; TaskbarList::_HwndGetTaskbarList(void)
0x18008a629  mov     r14, rax
0x18008a62c  test    rax, rax
0x18008a62f  jz      loc_18008A756
0x18008a635  xor     edx, edx; cbInit
0x18008a637  xor     ecx, ecx; pInit
0x18008a639  call    cs:__imp_SHCreateMemStream
0x18008a63f  mov     rbx, rax
0x18008a642  test    rax, rax
0x18008a645  jz      loc_18008A74F
0x18008a64b  mov     rdx, rax; pstm
0x18008a64e  mov     rcx, rsi; himl
0x18008a651  call    ImageList_Write
0x18008a656  test    eax, eax
0x18008a658  jz      loc_18008A73C
0x18008a65e  lea     rdx, [rbp+pui]; pui
0x18008a662  mov     qword ptr [rbp+pui], 0
0x18008a66a  mov     rcx, rbx; pstm
0x18008a66d  call    cs:__imp_IStream_Size
0x18008a673  test    eax, eax
0x18008a675  js      loc_18008A73C
0x18008a67b  lea     rdx, [rbp+dwProcessId]; lpdwProcessId
0x18008a67f  mov     [rbp+dwProcessId], 0
0x18008a686  mov     rcx, r14; hWnd
0x18008a689  call    cs:__imp_GetWindowThreadProcessId
0x18008a68f  mov     edx, dword ptr [rbp+pui]
0x18008a692  xor     ecx, ecx; pvData
0x18008a694  mov     r8d, [rbp+dwProcessId]; dwProcessId
0x18008a698  add     edx, 4; dwSize
0x18008a69b  call    cs:__imp_SHAllocShared
0x18008a6a1  mov     rsi, rax
0x18008a6a4  test    rax, rax
0x18008a6a7  jz      loc_18008A73C
0x18008a6ad  mov     edx, [rbp+dwProcessId]
0x18008a6b0  mov     r8d, 1
0x18008a6b6  mov     rcx, rax
0x18008a6b9  call    cs:__imp_SHLockSharedEx
0x18008a6bf  mov     r15, rax
0x18008a6c2  test    rax, rax
0x18008a6c5  jz      short loc_18008A730
0x18008a6c7  mov     eax, dword ptr [rbp+pui]
0x18008a6ca  mov     rcx, rbx; pstm
0x18008a6cd  mov     [r15], eax
0x18008a6d0  call    cs:__imp_IStream_Reset
0x18008a6d6  mov     r8d, dword ptr [rbp+pui]; cb
0x18008a6da  lea     rdx, [r15+4]; pv
0x18008a6de  mov     rcx, rbx; pstm
0x18008a6e1  call    cs:__imp_IStream_Read
0x18008a6e7  mov     rcx, r15; pvData
0x18008a6ea  call    cs:__imp_SHUnlockShared
0x18008a6f0  lea     rax, [rbp+dwResult]
0x18008a6f4  mov     [rbp+dwResult], 0
0x18008a6fc  mov     [rsp+50h+lpdwResult], rax; lpdwResult
0x18008a701  mov     r9, rsi; lParam
0x18008a704  mov     [rsp+50h+uTimeout], 0BB8h; uTimeout
0x18008a70c  mov     r8, r12; wParam
0x18008a70f  mov     edx, 44Eh; Msg
0x18008a714  mov     [rsp+50h+fuFlags], 2; fuFlags
0x18008a71c  mov     rcx, r14; hWnd
0x18008a71f  call    cs:__imp_SendMessageTimeoutW
0x18008a725  mov     rcx, rax
0x18008a728  xor     eax, eax
0x18008a72a  test    rcx, rcx
0x18008a72d  cmovnz  edi, eax
0x18008a730  mov     edx, [rbp+dwProcessId]; dwProcessId
0x18008a733  mov     rcx, rsi; hData
0x18008a736  call    cs:__imp_SHFreeShared
0x18008a73c  mov     rax, [rbx]
0x18008a73f  mov     rcx, rbx
0x18008a742  mov     rax, [rax+10h]
0x18008a746  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a74b  test    edi, edi
0x18008a74d  jns     short loc_18008A756
0x18008a74f  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18008a754  mov     edi, eax
0x18008a756  lea     r11, [rsp+50h+var_s0]
0x18008a75b  mov     eax, edi
0x18008a75d  mov     rbx, [r11+30h]
0x18008a761  mov     rsi, [r11+38h]
0x18008a765  mov     rsp, r11
0x18008a768  pop     r15
0x18008a76a  pop     r14
0x18008a76c  pop     r12
0x18008a76e  pop     rdi
0x18008a76f  pop     rbp
0x18008a770  retn
```
