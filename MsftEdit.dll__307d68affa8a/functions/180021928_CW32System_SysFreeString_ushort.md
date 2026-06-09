# CW32System::SysFreeString(ushort *)

- ea: `0x180021928`
- end: `0x1800219c0`
- name: `?SysFreeString@CW32System@@SAXPEAG@Z`
- size: `152`
- prototype: `void __fastcall(unsigned __int16 *)`
- caller_count: `93`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800080dc`
- `0x180021dc4`
- `0x1800311c0`
- `0x180033224`
- `0x18003e670`
- `0x180049838`
- `0x18004ebe0`
- `0x1800510e4`
- `0x18006913c`
- `0x18007574c`
- `0x180093e8c`
- `0x1800b5de0`
- `0x1800ddef0`
- `0x1800e1350`
- `0x1800e54a8`
- `0x1800e62d0`
- `0x1800e7b3c`
- `0x1800eb244`
- `0x1800f5e88`
- `0x1800fe528`
- `0x1800fe650`
- `0x1800fe810`
- `0x1800fecf0`
- `0x1801090a0`
- `0x18010fb74`
- `0x180128a64`
- `0x180128c00`
- `0x18012b664`
- `0x18012c524`
- `0x18012e2a0`
- `0x1801353dc`
- `0x18013664c`
- `0x18013a4d4`
- `0x1801464b0`
- `0x18014ebbc`
- `0x180154b6c`
- `0x180159884`
- `0x180159bb0`
- `0x18015a8ac`
- `0x18015ab5c`
- `0x18015afa8`
- `0x18015b9b4`
- `0x18015bd64`
- `0x18015d0c0`
- `0x18015d4a0`
- `0x18015f0cc`
- `0x180162040`
- `0x180164c0c`
- `0x18016f440`
- `0x180175104`

## callees

- `0x180021928`
- `0x18002ab44`
- `0x18002abb0`
- `0x18027a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180021997`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180021997`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002197b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002197b`

## string_xrefs

- `0x18002196e`: `oleaut32.dll`

## pseudocode

```c
void __fastcall CW32System::SysFreeString(unsigned __int16 *a1)
{
  void (__fastcall *v1)(unsigned __int16 *); // rax
  HMODULE Library; // rax
  unsigned int v4; // [rsp+38h] [rbp+10h] BYREF

  v1 = (void (__fastcall *)(unsigned __int16 *))qword_1802DD6F8;
  if ( qword_1802DD6F8 )
    goto LABEL_2;
  CWriteLock::CWriteLock(&v4, 0);
  if ( !qword_1802DD6F8 )
  {
    Library = hModule;
    if ( hModule || (Library = LoadLibraryExW(L"oleaut32.dll", 0, 0x800u), (hModule = Library) != 0) )
      qword_1802DD6F8 = (__int64)GetProcAddress(Library, "SysFreeString");
  }
  CWriteLock::~CWriteLock((CWriteLock *)&v4);
  v1 = (void (__fastcall *)(unsigned __int16 *))qword_1802DD6F8;
  if ( qword_1802DD6F8 )
LABEL_2:
    v1(a1);
}

```

## disassembly

```asm
0x180021928  push    rbx
0x18002192a  sub     rsp, 20h
0x18002192e  mov     rax, cs:qword_1802DD6F8
0x180021935  mov     rbx, rcx
0x180021938  test    rax, rax
0x18002193b  jz      short loc_18002194A
0x18002193d  mov     rcx, rbx
0x180021940  add     rsp, 20h
0x180021944  pop     rbx
0x180021945  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x18002194a  xor     edx, edx
0x18002194c  lea     rcx, [rsp+28h+arg_8]
0x180021951  call    ??0CWriteLock@@QEAA@W4LOCK_TYPE@@@Z; CWriteLock::CWriteLock(LOCK_TYPE)
0x180021956  cmp     cs:qword_1802DD6F8, 0
0x18002195e  jnz     short loc_1800219A4
0x180021960  mov     rax, cs:hModule
0x180021967  test    rax, rax
0x18002196a  jnz     short loc_18002198D
0x18002196c  xor     edx, edx; hFile
0x18002196e  lea     rcx, LibFileName; "oleaut32.dll"
0x180021975  mov     r8d, 800h; dwFlags
0x18002197b  call    cs:__imp_LoadLibraryExW
0x180021981  mov     cs:hModule, rax
0x180021988  test    rax, rax
0x18002198b  jz      short loc_1800219A4
0x18002198d  lea     rdx, ProcName; "SysFreeString"
0x180021994  mov     rcx, rax; hModule
0x180021997  call    cs:__imp_GetProcAddress
0x18002199d  mov     cs:qword_1802DD6F8, rax
0x1800219a4  lea     rcx, [rsp+28h+arg_8]; this
0x1800219a9  call    ??1CWriteLock@@QEAA@XZ; CWriteLock::~CWriteLock(void)
0x1800219ae  mov     rax, cs:qword_1802DD6F8
0x1800219b5  test    rax, rax
0x1800219b8  jnz     short loc_18002193D
0x1800219ba  add     rsp, 20h
0x1800219be  pop     rbx
0x1800219bf  retn
```
