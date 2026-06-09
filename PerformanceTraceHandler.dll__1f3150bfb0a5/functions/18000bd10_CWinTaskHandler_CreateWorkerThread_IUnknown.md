# CWinTaskHandler::CreateWorkerThread(IUnknown *)

- ea: `0x18000bd10`
- end: `0x18000be64`
- name: `?CreateWorkerThread@CWinTaskHandler@@AEAAJPEAUIUnknown@@@Z`
- size: `340`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, struct IUnknown *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x18000ced0`

## callees

- `0x18000bd10`
- `0x18001c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18000bd61`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18000bd61`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000be18`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000be18`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bd6f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bdcb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bd6f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bdcb`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18000be4c`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18000be4c`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000bdb6`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000bdb6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000be01`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000be01`

## pseudocode

```c
__int64 __fastcall CWinTaskHandler::CreateWorkerThread(CWinTaskHandler *this, struct IUnknown *a2)
{
  _QWORD *v2; // rsi
  signed int v4; // ebx
  signed int LastError; // eax
  HANDLE Thread; // rax
  signed int v7; // eax
  char *v8; // rcx
  HMODULE v9; // rcx
  signed __int32 v11[8]; // [rsp+0h] [rbp-38h] BYREF

  v2 = (_QWORD *)((char *)this + 48);
  v4 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, char *))a2->lpVtbl->QueryInterface)(
         a2,
         &GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a,
         (char *)this + 48);
  if ( v4 >= 0 )
  {
    if ( *((_DWORD *)this + 4) )
    {
      if ( GetModuleHandleExW(4u, (LPCWSTR)0x180000000LL, (HMODULE *)this + 3) )
      {
        v4 = 0;
      }
      else
      {
        LastError = GetLastError();
        v4 = LastError;
        if ( LastError > 0 )
          v4 = (unsigned __int16)LastError | 0x80070000;
        if ( v4 < 0 )
          goto LABEL_13;
      }
    }
    (*(void (__fastcall **)(CWinTaskHandler *))(*(_QWORD *)this + 8LL))(this);
    Thread = CreateThread(0, 0, CWinTaskHandler::WorkerThreadProc, this, 4u, 0);
    *((_QWORD *)this + 5) = Thread;
    if ( (((unsigned __int64)Thread + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    {
      v7 = GetLastError();
      v4 = v7;
      if ( v7 > 0 )
        v4 = (unsigned __int16)v7 | 0x80070000;
      (*(void (__fastcall **)(CWinTaskHandler *))(*(_QWORD *)this + 16LL))(this);
    }
  }
  if ( v4 >= 0 )
  {
    _InterlockedOr(v11, 0);
    ResumeThread(*((HANDLE *)this + 5));
    return (unsigned int)v4;
  }
LABEL_13:
  v8 = (char *)*((_QWORD *)this + 5);
  if ( (unsigned __int64)(v8 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    CloseHandle(v8);
    *((_QWORD *)this + 5) = -1;
  }
  v9 = (HMODULE)*((_QWORD *)this + 3);
  if ( v9 )
  {
    FreeLibrary(v9);
    *((_QWORD *)this + 3) = 0;
  }
  if ( *v2 )
  {
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v2 + 16LL))(*v2);
    *v2 = 0;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000bd10  mov     [rsp+arg_0], rbx
0x18000bd15  mov     [rsp+arg_8], rsi
0x18000bd1a  push    rdi
0x18000bd1b  sub     rsp, 30h
0x18000bd1f  mov     rax, [rdx]
0x18000bd22  lea     rsi, [rcx+30h]
0x18000bd26  mov     r9, rdx
0x18000bd29  mov     rdi, rcx
0x18000bd2c  mov     r8, rsi
0x18000bd2f  lea     rdx, _GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a
0x18000bd36  mov     rcx, r9
0x18000bd39  mov     rax, [rax]
0x18000bd3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bd41  mov     ebx, eax
0x18000bd43  test    eax, eax
0x18000bd45  js      loc_18000BDEF
0x18000bd4b  cmp     dword ptr [rdi+10h], 0
0x18000bd4f  jz      short loc_18000BD88
0x18000bd51  lea     r8, [rdi+18h]; phModule
0x18000bd55  mov     ecx, 4; dwFlags
0x18000bd5a  lea     rdx, cs:180000000h; lpModuleName
0x18000bd61  call    cs:__imp_GetModuleHandleExW
0x18000bd67  test    eax, eax
0x18000bd69  jz      short loc_18000BD6F
0x18000bd6b  xor     ebx, ebx
0x18000bd6d  jmp     short loc_18000BD88
0x18000bd6f  call    cs:__imp_GetLastError
0x18000bd75  mov     ebx, eax
0x18000bd77  test    eax, eax
0x18000bd79  jle     short loc_18000BD84
0x18000bd7b  movzx   ebx, ax
0x18000bd7e  or      ebx, 80070000h
0x18000bd84  test    ebx, ebx
0x18000bd86  js      short loc_18000BDF3
0x18000bd88  mov     rax, [rdi]
0x18000bd8b  mov     rcx, rdi
0x18000bd8e  mov     rax, [rax+8]
0x18000bd92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bd97  mov     r9, rdi; lpParameter
0x18000bd9a  mov     [rsp+38h+lpThreadId], 0; lpThreadId
0x18000bda3  lea     r8, ?WorkerThreadProc@CWinTaskHandler@@CAKPEAX@Z; lpStartAddress
0x18000bdaa  mov     [rsp+38h+dwCreationFlags], 4; dwCreationFlags
0x18000bdb2  xor     edx, edx; dwStackSize
0x18000bdb4  xor     ecx, ecx; lpThreadAttributes
0x18000bdb6  call    cs:__imp_CreateThread
0x18000bdbc  mov     [rdi+28h], rax
0x18000bdc0  inc     rax
0x18000bdc3  test    rax, 0FFFFFFFFFFFFFFFEh
0x18000bdc9  jnz     short loc_18000BDEF
0x18000bdcb  call    cs:__imp_GetLastError
0x18000bdd1  mov     ebx, eax
0x18000bdd3  test    eax, eax
0x18000bdd5  jle     short loc_18000BDE0
0x18000bdd7  movzx   ebx, ax
0x18000bdda  or      ebx, 80070000h
0x18000bde0  mov     rax, [rdi]
0x18000bde3  mov     rcx, rdi
0x18000bde6  mov     rax, [rax+10h]
0x18000bdea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bdef  test    ebx, ebx
0x18000bdf1  jns     short loc_18000BE43
0x18000bdf3  mov     rcx, [rdi+28h]; hObject
0x18000bdf7  lea     rax, [rcx-1]
0x18000bdfb  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000bdff  ja      short loc_18000BE0F
0x18000be01  call    cs:__imp_CloseHandle
0x18000be07  mov     qword ptr [rdi+28h], 0FFFFFFFFFFFFFFFFh
0x18000be0f  mov     rcx, [rdi+18h]; hLibModule
0x18000be13  test    rcx, rcx
0x18000be16  jz      short loc_18000BE26
0x18000be18  call    cs:__imp_FreeLibrary
0x18000be1e  mov     qword ptr [rdi+18h], 0
0x18000be26  mov     rcx, [rsi]
0x18000be29  test    rcx, rcx
0x18000be2c  jz      short loc_18000BE52
0x18000be2e  mov     rax, [rcx]
0x18000be31  mov     rax, [rax+10h]
0x18000be35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be3a  mov     qword ptr [rsi], 0
0x18000be41  jmp     short loc_18000BE52
0x18000be43  lock or [rsp+38h+var_38], 0
0x18000be48  mov     rcx, [rdi+28h]; hThread
0x18000be4c  call    cs:__imp_ResumeThread
0x18000be52  mov     rsi, [rsp+38h+arg_8]
0x18000be57  mov     eax, ebx
0x18000be59  mov     rbx, [rsp+38h+arg_0]
0x18000be5e  add     rsp, 30h
0x18000be62  pop     rdi
0x18000be63  retn
```
