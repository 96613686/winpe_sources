# Udm::AddUserDataServiceDllReference(void)

- ea: `0x1800c5b10`
- end: `0x1800c5b7d`
- name: `?AddUserDataServiceDllReference@Udm@@YAXXZ`
- size: `109`
- prototype: `void __fastcall(Udm *__hidden this)`
- caller_count: `9`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x1800baa10`
- `0x1800bac60`
- `0x1800bade8`
- `0x1800bcc78`
- `0x1800be744`
- `0x1800be7fc`
- `0x1800c1288`
- `0x1800c1340`
- `0x1800c13f8`

## callees

- `0x1800c5b10`
- `0x1800c5c48`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800c5b45`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800c5b45`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c5b76`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800c5b1d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800c5b1d`

## string_xrefs

- `0x1800c5b38`: `UserDataService.dll`

## pseudocode

```c
void __fastcall Udm::AddUserDataServiceDllReference(Udm *this)
{
  HMODULE Library; // rbx

  EnterCriticalSection(&stru_1800FE808);
  if ( ++dword_1800FE608 == 1 )
  {
    Library = LoadLibraryExW(L"UserDataService.dll", 0, 0x800u);
    if ( Library != lpParameter )
    {
      tlx::auto_xxx<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),0>::_Delete(&lpParameter);
      lpParameter = Library;
    }
  }
  LeaveCriticalSection(&stru_1800FE808);
}

```

## disassembly

```asm
0x1800c5b10  push    rbx
0x1800c5b12  sub     rsp, 20h
0x1800c5b16  lea     rcx, stru_1800FE808; lpCriticalSection
0x1800c5b1d  call    cs:__imp_EnterCriticalSection
0x1800c5b23  mov     eax, cs:dword_1800FE608
0x1800c5b29  inc     eax
0x1800c5b2b  mov     cs:dword_1800FE608, eax
0x1800c5b31  cmp     eax, 1
0x1800c5b34  jnz     short loc_1800C5B6A
0x1800c5b36  xor     edx, edx; hFile
0x1800c5b38  lea     rcx, aUserdataservic; "UserDataService.dll"
0x1800c5b3f  mov     r8d, 800h; dwFlags
0x1800c5b45  call    cs:__imp_LoadLibraryExW
0x1800c5b4b  cmp     rax, cs:lpParameter
0x1800c5b52  mov     rbx, rax
0x1800c5b55  jz      short loc_1800C5B6A
0x1800c5b57  lea     rcx, lpParameter
0x1800c5b5e  call    ?_Delete@?$auto_xxx@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),0>::_Delete(void)
0x1800c5b63  mov     cs:lpParameter, rbx
0x1800c5b6a  lea     rcx, stru_1800FE808
0x1800c5b71  add     rsp, 20h
0x1800c5b75  pop     rbx
0x1800c5b76  jmp     cs:__imp_LeaveCriticalSection
```
