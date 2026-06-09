# Udm::ReleaseUserDataServiceDllReference(void)

- ea: `0x1800c5bb8`
- end: `0x1800c5c40`
- name: `?ReleaseUserDataServiceDllReference@Udm@@YAXXZ`
- size: `136`
- prototype: `void __fastcall(Udm *__hidden this)`
- caller_count: `8`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callers

- `0x1800baf38`
- `0x1800bafd0`
- `0x1800bcd30`
- `0x1800be934`
- `0x1800be9dc`
- `0x1800c1708`
- `0x1800c17b0`
- `0x1800c1858`

## callees

- `0x1800237dc`
- `0x1800c5bb8`
- `0x1800c5c48`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c5c39`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800c5bc3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800c5bc3`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800c5bfd`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800c5bfd`

## pseudocode

```c
void __fastcall Udm::ReleaseUserDataServiceDllReference(Udm *this)
{
  HANDLE Thread; // [rsp+40h] [rbp+8h] BYREF

  EnterCriticalSection(&stru_1800FE808);
  if ( !--dword_1800FE608 )
  {
    Thread = CreateThread(0, 0, Udm::ReleaseLibraryReference, lpParameter, 0, 0);
    if ( !Thread )
      tlx::auto_xxx<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),0>::_Delete(&lpParameter);
    lpParameter = 0;
    tlx::auto_xxx<void *,int (*)(void *),&int CloseHandle(void *),0>::_Delete(&Thread);
  }
  LeaveCriticalSection(&stru_1800FE808);
}

```

## disassembly

```asm
0x1800c5bb8  sub     rsp, 38h
0x1800c5bbc  lea     rcx, stru_1800FE808; lpCriticalSection
0x1800c5bc3  call    cs:__imp_EnterCriticalSection
0x1800c5bc9  mov     eax, cs:dword_1800FE608
0x1800c5bcf  sub     eax, 1
0x1800c5bd2  mov     cs:dword_1800FE608, eax
0x1800c5bd8  jnz     short loc_1800C5C2E
0x1800c5bda  mov     r9, cs:lpParameter; lpParameter
0x1800c5be1  lea     r8, Udm__ReleaseLibraryReference; lpStartAddress
0x1800c5be8  mov     [rsp+38h+lpThreadId], 0; lpThreadId
0x1800c5bf1  xor     edx, edx; dwStackSize
0x1800c5bf3  xor     ecx, ecx; lpThreadAttributes
0x1800c5bf5  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x1800c5bfd  call    cs:__imp_CreateThread
0x1800c5c03  mov     [rsp+38h+arg_0], rax
0x1800c5c08  test    rax, rax
0x1800c5c0b  jnz     short loc_1800C5C19
0x1800c5c0d  lea     rcx, lpParameter
0x1800c5c14  call    ?_Delete@?$auto_xxx@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),0>::_Delete(void)
0x1800c5c19  lea     rcx, [rsp+38h+arg_0]
0x1800c5c1e  mov     cs:lpParameter, 0
0x1800c5c29  call    ?_Delete@?$auto_xxx@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<void *,int (*)(void *),&CloseHandle(void *),0>::_Delete(void)
0x1800c5c2e  lea     rcx, stru_1800FE808
0x1800c5c35  add     rsp, 38h
0x1800c5c39  jmp     cs:__imp_LeaveCriticalSection
```
