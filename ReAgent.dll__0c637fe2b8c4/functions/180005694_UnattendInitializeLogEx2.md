# UnattendInitializeLogEx2

- ea: `0x180005694`
- end: `0x1800057a8`
- name: `UnattendInitializeLogEx2`
- size: `276`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `77`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18000efb0`
- `0x180019180`
- `0x180019240`
- `0x180019a90`
- `0x18001a700`
- `0x18001a7c0`
- `0x18001a8d0`
- `0x18001aa00`
- `0x18001ab30`
- `0x18001e0e0`
- `0x18001e870`
- `0x180020120`
- `0x180020220`
- `0x180020400`
- `0x180020760`
- `0x1800207b0`
- `0x180020850`
- `0x1800209a0`
- `0x180020a40`
- `0x180020d20`
- `0x180021060`
- `0x1800213e0`
- `0x180021760`
- `0x180021df0`
- `0x180021e90`
- `0x1800224f0`
- `0x180022910`
- `0x1800230b0`
- `0x1800234f0`
- `0x180023590`
- `0x1800237a0`
- `0x180023a20`
- `0x180023ad0`
- `0x180023b50`
- `0x180023f20`
- `0x1800243f0`
- `0x180024770`
- `0x180024800`
- `0x180024a10`
- `0x180024df0`
- `0x180024f60`
- `0x180024ff0`
- `0x180025560`
- `0x180025920`
- `0x1800259d0`
- `0x1800260c0`
- `0x180026460`
- `0x180026670`
- `0x180026a40`
- `0x180026ea0`

## callees

- `0x1800053b4`
- `0x180005694`
- `0x1800062f4`
- `0x180007098`
- `0x18005f010`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18000578a`
- `KERNEL32!HeapFree` at `0x18000578a`
- `KERNEL32!GetProcessHeap` at `0x18000577c`
- `KERNEL32!GetProcessHeap` at `0x18000577c`
- `KERNEL32!FreeLibrary` at `0x180005771`
- `KERNEL32!FreeLibrary` at `0x180005771`
- `KERNEL32!EnterCriticalSection` at `0x1800056a7`
- `KERNEL32!EnterCriticalSection` at `0x1800056a7`
- `KERNEL32!LeaveCriticalSection` at `0x1800057a1`
- `KERNEL32!LoadLibraryExW` at `0x1800056f5`
- `KERNEL32!LoadLibraryExW` at `0x1800056f5`

## string_xrefs

- `0x1800056ec`: `wdscore.dll`

## pseudocode

```c
void __fastcall UnattendInitializeLogEx2(int a1)
{
  unsigned __int16 *v2; // rbx
  unsigned __int16 *Expand; // rax
  HMODULE Library; // rax
  HANDLE ProcessHeap; // rax

  EnterCriticalSection(&CriticalSection);
  ++dword_1800ADBD0;
  if ( dword_1800ADBC0 )
    goto LABEL_17;
  v2 = 0;
  hLibModule = 0;
  if ( !a1 )
  {
    Expand = (unsigned __int16 *)AllocateExpand(L"%windir%\\Panther\\UnattendGC");
    v2 = Expand;
    if ( Expand )
      CreatePath(Expand);
  }
  Library = LoadLibraryExW(L"wdscore.dll", 0, 0);
  hLibModule = Library;
  if ( !Library )
    goto LABEL_12;
  if ( (int)InitFuncPointerTable() < 0 )
    goto LABEL_11;
  if ( a1 )
  {
    dword_1800ADBC0 = 1;
    dword_1800ADBF8 = 0;
    goto LABEL_11;
  }
  if ( !qword_1800ADBB8 )
  {
LABEL_11:
    Library = hLibModule;
LABEL_12:
    if ( !dword_1800ADBC0 && Library )
      FreeLibrary(Library);
    goto LABEL_15;
  }
  qword_1800ADBB8(0, 50393088, v2);
  dword_1800ADBC0 = 1;
  dword_1800ADBF8 = 1;
LABEL_15:
  if ( v2 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v2);
  }
LABEL_17:
  LeaveCriticalSection(&CriticalSection);
}

```

## disassembly

```asm
0x180005694  mov     [rsp+arg_0], rbx
0x180005699  push    rdi
0x18000569a  sub     rsp, 20h
0x18000569e  mov     edi, ecx
0x1800056a0  lea     rcx, CriticalSection; lpCriticalSection
0x1800056a7  call    cs:__imp_EnterCriticalSection
0x1800056ad  inc     cs:dword_1800ADBD0
0x1800056b3  cmp     cs:dword_1800ADBC0, 0
0x1800056ba  jnz     loc_180005790
0x1800056c0  xor     ebx, ebx
0x1800056c2  mov     cs:hLibModule, rbx
0x1800056c9  test    edi, edi
0x1800056cb  jnz     short loc_1800056E9
0x1800056cd  lea     rcx, Src; "%windir%\\Panther\\UnattendGC"
0x1800056d4  call    AllocateExpand
0x1800056d9  mov     rbx, rax
0x1800056dc  test    rax, rax
0x1800056df  jz      short loc_1800056E9
0x1800056e1  mov     rcx, rax
0x1800056e4  call    CreatePath
0x1800056e9  xor     r8d, r8d; dwFlags
0x1800056ec  lea     rcx, aWdscoreDll; "wdscore.dll"
0x1800056f3  xor     edx, edx; hFile
0x1800056f5  call    cs:__imp_LoadLibraryExW
0x1800056fb  mov     cs:hLibModule, rax
0x180005702  test    rax, rax
0x180005705  jz      short loc_180005760
0x180005707  call    InitFuncPointerTable
0x18000570c  test    eax, eax
0x18000570e  js      short loc_180005759
0x180005710  test    edi, edi
0x180005712  jnz     short loc_180005745
0x180005714  mov     rax, cs:qword_1800ADBB8
0x18000571b  test    rax, rax
0x18000571e  jz      short loc_180005759
0x180005720  mov     r8, rbx
0x180005723  mov     edx, 300F000h
0x180005728  xor     ecx, ecx
0x18000572a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000572f  mov     cs:dword_1800ADBC0, 1
0x180005739  mov     cs:dword_1800ADBF8, 1
0x180005743  jmp     short loc_180005777
0x180005745  mov     cs:dword_1800ADBC0, 1
0x18000574f  mov     cs:dword_1800ADBF8, 0
0x180005759  mov     rax, cs:hLibModule
0x180005760  cmp     cs:dword_1800ADBC0, 0
0x180005767  jnz     short loc_180005777
0x180005769  test    rax, rax
0x18000576c  jz      short loc_180005777
0x18000576e  mov     rcx, rax; hLibModule
0x180005771  call    cs:__imp_FreeLibrary
0x180005777  test    rbx, rbx
0x18000577a  jz      short loc_180005790
0x18000577c  call    cs:__imp_GetProcessHeap
0x180005782  mov     r8, rbx; lpMem
0x180005785  xor     edx, edx; dwFlags
0x180005787  mov     rcx, rax; hHeap
0x18000578a  call    cs:__imp_HeapFree
0x180005790  lea     rcx, CriticalSection
0x180005797  mov     rbx, [rsp+28h+arg_0]
0x18000579c  add     rsp, 20h
0x1800057a0  pop     rdi
0x1800057a1  jmp     cs:__imp_LeaveCriticalSection
```
