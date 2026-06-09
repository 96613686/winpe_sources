# CEditionUpgradeBroker::ShowProductKeyUI(void)

- ea: `0x18000a390`
- end: `0x18000a472`
- name: `?ShowProductKeyUI@CEditionUpgradeBroker@@UEAAJXZ`
- size: `226`
- prototype: `__int64 __fastcall(CEditionUpgradeBroker *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800024d4`
- `0x180008740`
- `0x180008c60`
- `0x180009978`
- `0x18000a390`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a448`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a448`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a457`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a457`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a417`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a417`
- `SHELL32!ShellExecuteExW` at `0x18000a40d`
- `SHELL32!ShellExecuteExW` at `0x18000a40d`

## pseudocode

```c
__int64 __fastcall CEditionUpgradeBroker::ShowProductKeyUI(CEditionUpgradeBroker *this)
{
  __int64 v2; // rcx
  int v3; // eax
  const WCHAR *v4; // rbx
  unsigned int v5; // edi
  __int64 v6; // rcx
  signed int LastError; // eax
  HANDLE ProcessHeap; // rax
  SHELLEXECUTEINFOW pExecInfo; // [rsp+20h] [rbp-39h] BYREF
  const WCHAR *v11; // [rsp+C8h] [rbp+6Fh] BYREF

  v11 = 0;
  memset_0(&pExecInfo, 0, sizeof(pExecInfo));
  v3 = CMiscHelpersT<CEmptyType>::AppendToSystemPath(v2, &v11);
  v4 = v11;
  v5 = v3;
  if ( v3 >= 0 )
  {
    pExecInfo.cbSize = 112;
    pExecInfo.lpVerb = L"Open";
    pExecInfo.lpFile = v11;
    pExecInfo.lpParameters = (LPCWSTR)&qword_1800298A8;
    pExecInfo.hwnd = (HWND)*((int *)this + 10);
    pExecInfo.fMask = 64;
    pExecInfo.nShow = 1;
    if ( ShellExecuteExW(&pExecInfo) )
      goto LABEL_10;
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v5 = -2147467259;
    }
    v6 = v5;
  }
  else
  {
    v6 = (unsigned int)v3;
  }
  CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v6);
LABEL_10:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v5);
  if ( v4 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, (LPVOID)(v4 - 2));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  return v5;
}

```

## disassembly

```asm
0x18000a390  push    rbp
0x18000a392  push    rbx
0x18000a393  push    rsi
0x18000a394  push    rdi
0x18000a395  lea     rbp, [rsp-3Fh]
0x18000a39a  sub     rsp, 98h
0x18000a3a1  xor     edx, edx; Val
0x18000a3a3  mov     [rbp+57h+arg_8], 0
0x18000a3ab  mov     rsi, rcx
0x18000a3ae  lea     rcx, [rbp+57h+pExecInfo]; void *
0x18000a3b2  lea     r8d, [rdx+70h]; Size
0x18000a3b6  call    memset_0
0x18000a3bb  lea     rdx, [rbp+57h+arg_8]
0x18000a3bf  call    ?AppendToSystemPath@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBGPEAPEAG@Z; CMiscHelpersT<CEmptyType>::AppendToSystemPath(ushort const *,ushort * *)
0x18000a3c4  mov     rbx, [rbp+57h+arg_8]
0x18000a3c8  mov     edi, eax
0x18000a3ca  test    eax, eax
0x18000a3cc  jns     short loc_18000A3D2
0x18000a3ce  mov     ecx, eax
0x18000a3d0  jmp     short loc_18000A437
0x18000a3d2  lea     rax, aOpen; "Open"
0x18000a3d9  mov     [rbp+57h+pExecInfo.cbSize], 70h ; 'p'
0x18000a3e0  mov     [rbp+57h+pExecInfo.lpVerb], rax
0x18000a3e4  lea     rcx, [rbp+57h+pExecInfo]; pExecInfo
0x18000a3e8  lea     rax, qword_1800298A8
0x18000a3ef  mov     [rbp+57h+pExecInfo.lpFile], rbx
0x18000a3f3  mov     [rbp+57h+pExecInfo.lpParameters], rax
0x18000a3f7  movsxd  rax, dword ptr [rsi+28h]
0x18000a3fb  mov     [rbp+57h+pExecInfo.hwnd], rax
0x18000a3ff  mov     [rbp+57h+pExecInfo.fMask], 40h ; '@'
0x18000a406  mov     [rbp+57h+pExecInfo.nShow], 1
0x18000a40d  call    cs:__imp_ShellExecuteExW
0x18000a413  test    eax, eax
0x18000a415  jnz     short loc_18000A43C
0x18000a417  call    cs:__imp_GetLastError
0x18000a41d  mov     edi, eax
0x18000a41f  test    eax, eax
0x18000a421  jnz     short loc_18000A42A
0x18000a423  mov     edi, 80004005h
0x18000a428  jmp     short loc_18000A435
0x18000a42a  jle     short loc_18000A435
0x18000a42c  movzx   edi, ax
0x18000a42f  or      edi, 80070000h
0x18000a435  mov     ecx, edi
0x18000a437  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18000a43c  mov     ecx, edi
0x18000a43e  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000a443  test    rbx, rbx
0x18000a446  jz      short loc_18000A464
0x18000a448  call    cs:__imp_GetProcessHeap
0x18000a44e  lea     r8, [rbx-4]; lpMem
0x18000a452  xor     edx, edx; dwFlags
0x18000a454  mov     rcx, rax; hHeap
0x18000a457  call    cs:__imp_HeapFree
0x18000a45d  xor     ecx, ecx
0x18000a45f  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000a464  mov     eax, edi
0x18000a466  add     rsp, 98h
0x18000a46d  pop     rdi
0x18000a46e  pop     rsi
0x18000a46f  pop     rbx
0x18000a470  pop     rbp
0x18000a471  retn
```
