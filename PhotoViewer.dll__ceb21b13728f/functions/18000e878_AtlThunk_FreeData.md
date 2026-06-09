# AtlThunk_FreeData

- ea: `0x18000e878`
- end: `0x18000e986`
- name: `AtlThunk_FreeData`
- size: `270`
- prototype: `void __stdcall(AtlThunkData_t *Thunk)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18000e30c`
- `0x18000e858`

## callees

- `0x18000e878`
- `0x180077c04`
- `0x180077cf4`
- `0x180080010`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18000e975`
- `KERNEL32!HeapFree` at `0x18000e975`
- `KERNEL32!GetProcessHeap` at `0x18000e967`
- `KERNEL32!GetProcessHeap` at `0x18000e967`
- `KERNEL32!LoadLibraryExA` at `0x18000e8c6`
- `KERNEL32!LoadLibraryExA` at `0x18000e8c6`
- `KERNEL32!DecodePointer` at `0x18000e953`
- `KERNEL32!DecodePointer` at `0x18000e953`

## string_xrefs

- `0x18000e8b9`: `atlthunk.dll`

## pseudocode

```c
void __stdcall AtlThunk_FreeData(AtlThunkData_t *Thunk)
{
  struct _SLIST_ENTRY *v2; // rcx
  HMODULE Library; // rax
  HMODULE v4; // rdi
  void (__fastcall *v5)(_QWORD); // rax
  HANDLE ProcessHeap; // rax
  signed __int32 v7[10]; // [rsp+0h] [rbp-28h] BYREF

  if ( Thunk )
  {
    v2 = (struct _SLIST_ENTRY *)*((_QWORD *)Thunk + 1);
    if ( v2 )
    {
      if ( *(_DWORD *)Thunk )
      {
        __FreeStdCallThunk_cmn(v2);
      }
      else
      {
        if ( !byte_1800A3DF4 )
        {
          Library = LoadLibraryExA("atlthunk.dll", 0, 0x800u);
          v4 = Library;
          if ( !Library
            || !(unsigned __int8)GetProcAddressSingle(Library, "AtlThunk_AllocateData", &qword_1800A4630)
            || !(unsigned __int8)GetProcAddressSingle(v4, "AtlThunk_InitData", &qword_1800A4628)
            || !(unsigned __int8)GetProcAddressSingle(v4, "AtlThunk_DataToCode", &qword_1800A4620)
            || !(unsigned __int8)GetProcAddressSingle(v4, "AtlThunk_FreeData", &Ptr) )
          {
            goto LABEL_14;
          }
          _InterlockedOr(v7, 0);
          byte_1800A3DF4 = 1;
        }
        v5 = (void (__fastcall *)(_QWORD))DecodePointer(Ptr);
        if ( v5 )
          v5(*((_QWORD *)Thunk + 1));
      }
    }
LABEL_14:
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, Thunk);
  }
}

```

## disassembly

```asm
0x18000e878  test    rcx, rcx
0x18000e87b  jz      locret_18000E985
0x18000e881  mov     [rsp+arg_0], rbx
0x18000e886  push    rdi
0x18000e887  sub     rsp, 20h
0x18000e88b  mov     rbx, rcx
0x18000e88e  mov     rcx, [rcx+8]; ListEntry
0x18000e892  test    rcx, rcx
0x18000e895  jz      loc_18000E967
0x18000e89b  cmp     dword ptr [rbx], 0
0x18000e89e  jz      short loc_18000E8AA
0x18000e8a0  call    ?__FreeStdCallThunk_cmn@@YAXPEAX@Z; __FreeStdCallThunk_cmn(void *)
0x18000e8a5  jmp     loc_18000E967
0x18000e8aa  cmp     cs:byte_1800A3DF4, 0
0x18000e8b1  jnz     loc_18000E94C
0x18000e8b7  xor     edx, edx; hFile
0x18000e8b9  lea     rcx, LibFileName; "atlthunk.dll"
0x18000e8c0  mov     r8d, 800h; dwFlags
0x18000e8c6  call    cs:__imp_LoadLibraryExA
0x18000e8cc  mov     rdi, rax
0x18000e8cf  test    rax, rax
0x18000e8d2  jz      loc_18000E967
0x18000e8d8  lea     r8, qword_1800A4630
0x18000e8df  mov     rcx, rax
0x18000e8e2  lea     rdx, aAtlthunkAlloca; "AtlThunk_AllocateData"
0x18000e8e9  call    GetProcAddressSingle
0x18000e8ee  test    al, al
0x18000e8f0  jz      short loc_18000E967
0x18000e8f2  lea     r8, qword_1800A4628
0x18000e8f9  mov     rcx, rdi
0x18000e8fc  lea     rdx, aAtlthunkInitda; "AtlThunk_InitData"
0x18000e903  call    GetProcAddressSingle
0x18000e908  test    al, al
0x18000e90a  jz      short loc_18000E967
0x18000e90c  lea     r8, qword_1800A4620
0x18000e913  mov     rcx, rdi
0x18000e916  lea     rdx, aAtlthunkDatato; "AtlThunk_DataToCode"
0x18000e91d  call    GetProcAddressSingle
0x18000e922  test    al, al
0x18000e924  jz      short loc_18000E967
0x18000e926  lea     r8, Ptr
0x18000e92d  mov     rcx, rdi
0x18000e930  lea     rdx, aAtlthunkFreeda; "AtlThunk_FreeData"
0x18000e937  call    GetProcAddressSingle
0x18000e93c  test    al, al
0x18000e93e  jz      short loc_18000E967
0x18000e940  lock or [rsp+28h+var_28], 0
0x18000e945  mov     cs:byte_1800A3DF4, 1
0x18000e94c  mov     rcx, cs:Ptr; Ptr
0x18000e953  call    cs:__imp_DecodePointer
0x18000e959  test    rax, rax
0x18000e95c  jz      short loc_18000E967
0x18000e95e  mov     rcx, [rbx+8]
0x18000e962  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e967  call    cs:__imp_GetProcessHeap
0x18000e96d  mov     r8, rbx; lpMem
0x18000e970  xor     edx, edx; dwFlags
0x18000e972  mov     rcx, rax; hHeap
0x18000e975  call    cs:__imp_HeapFree
0x18000e97b  mov     rbx, [rsp+28h+arg_0]
0x18000e980  add     rsp, 20h
0x18000e984  pop     rdi
0x18000e985  retn
```
