# CSystemMSIController::s_ProgressDialogCallback(HWND__ *,uint,unsigned __int64,__int64,__int64)

- ea: `0x18003f8e0`
- end: `0x18003f9a3`
- name: `?s_ProgressDialogCallback@CSystemMSIController@@SAJPEAUHWND__@@I_K_J2@Z`
- size: `195`
- prototype: `__int64 __usercall@<rax>(HWND hWnd@<rcx>, unsigned int@<edx>, unsigned __int64@<r8>, __int64@<r9>, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x18003f8e0`

## import_xrefs

- `SHCORE!SHCreateThread` at `0x18003f96e`
- `SHCORE!SHCreateThread` at `0x18003f96e`
- `USER32!SendMessageW` at `0x18003f925`
- `USER32!SendMessageW` at `0x18003f942`
- `USER32!SendMessageW` at `0x18003f957`
- `USER32!SendMessageW` at `0x18003f925`
- `USER32!SendMessageW` at `0x18003f942`
- `USER32!SendMessageW` at `0x18003f957`
- `USER32!PostMessageW` at `0x18003f98f`
- `USER32!PostMessageW` at `0x18003f98f`

## pseudocode

```c
__int64 __fastcall CSystemMSIController::s_ProgressDialogCallback(HWND hWnd, int a2, int a3, __int64 a4, _DWORD *pData)
{
  unsigned int v6; // ebx

  if ( a2 )
  {
    v6 = 0;
    if ( a2 == 2 && a3 == 2 )
    {
      v6 = 1;
      pData[10] = 1;
    }
  }
  else
  {
    SendMessageW(hWnd, 0x46Fu, 1u, 0);
    *((_QWORD *)pData + 4) = hWnd;
    SendMessageW(hWnd, 0x467u, 1u, 0);
    SendMessageW(hWnd, 0x46Bu, 1u, 100);
    if ( SHCreateThread(CSystemMSIController::s_AsyncMSIWorker, pData, 8u, 0) )
    {
      return 0;
    }
    else
    {
      v6 = -2147467259;
      PostMessageW(hWnd, 0x466u, 1u, 0);
      pData[4] = -2147467259;
    }
  }
  return v6;
}

```

## disassembly

```asm
0x18003f8e0  push    rbx
0x18003f8e2  push    rbp
0x18003f8e3  push    rsi
0x18003f8e4  push    rdi
0x18003f8e5  sub     rsp, 28h
0x18003f8e9  mov     rsi, rcx
0x18003f8ec  test    edx, edx
0x18003f8ee  jz      short loc_18003F916
0x18003f8f0  xor     ebx, ebx
0x18003f8f2  cmp     edx, 2
0x18003f8f5  jnz     loc_18003F998
0x18003f8fb  cmp     r8d, edx
0x18003f8fe  jnz     loc_18003F998
0x18003f904  mov     rax, [rsp+48h+pData]
0x18003f909  lea     edi, [rbx+1]
0x18003f90c  mov     ebx, edi
0x18003f90e  mov     [rax+28h], edi
0x18003f911  jmp     loc_18003F998
0x18003f916  xor     r9d, r9d; lParam
0x18003f919  mov     edx, 46Fh; Msg
0x18003f91e  lea     edi, [r9+1]
0x18003f922  mov     r8d, edi; wParam
0x18003f925  call    cs:__imp_SendMessageW
0x18003f92b  mov     rbp, [rsp+48h+pData]
0x18003f930  xor     r9d, r9d; lParam
0x18003f933  mov     r8d, edi; wParam
0x18003f936  mov     edx, 467h; Msg
0x18003f93b  mov     rcx, rsi; hWnd
0x18003f93e  mov     [rbp+20h], rsi
0x18003f942  call    cs:__imp_SendMessageW
0x18003f948  lea     r9d, [rdi+63h]; lParam
0x18003f94c  mov     r8d, edi; wParam
0x18003f94f  mov     edx, 46Bh; Msg
0x18003f954  mov     rcx, rsi; hWnd
0x18003f957  call    cs:__imp_SendMessageW
0x18003f95d  xor     r9d, r9d; pfnCallback
0x18003f960  lea     r8d, [rdi+7]; flags
0x18003f964  mov     rdx, rbp; pData
0x18003f967  lea     rcx, ?s_AsyncMSIWorker@CSystemMSIController@@CAKPEAX@Z; pfnThreadProc
0x18003f96e  call    cs:__imp_SHCreateThread
0x18003f974  test    eax, eax
0x18003f976  jz      short loc_18003F97C
0x18003f978  xor     ebx, ebx
0x18003f97a  jmp     short loc_18003F998
0x18003f97c  xor     r9d, r9d; lParam
0x18003f97f  mov     r8, rdi; wParam
0x18003f982  mov     edx, 466h; Msg
0x18003f987  mov     rcx, rsi; hWnd
0x18003f98a  mov     ebx, 80004005h
0x18003f98f  call    cs:__imp_PostMessageW
0x18003f995  mov     [rbp+10h], ebx
0x18003f998  mov     eax, ebx
0x18003f99a  add     rsp, 28h
0x18003f99e  pop     rdi
0x18003f99f  pop     rsi
0x18003f9a0  pop     rbp
0x18003f9a1  pop     rbx
0x18003f9a2  retn
```
