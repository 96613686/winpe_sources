# CJournal::ReportDriverError(long,char const *)

- ea: `0x18007efa0`
- end: `0x18007f04c`
- name: `?ReportDriverError@CJournal@@QEAAXJPEBD@Z`
- size: `172`
- prototype: `void __fastcall(CJournal *__hidden this, int, const char *)`
- caller_count: `64`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180003810`
- `0x180004460`
- `0x180006bc0`
- `0x18000de64`
- `0x180024ed8`
- `0x180028070`
- `0x18003d69c`
- `0x1800446cc`
- `0x180052f98`
- `0x180053830`
- `0x180054550`
- `0x180055294`
- `0x180057ce8`
- `0x18005dca0`
- `0x180067c30`
- `0x18006f4a0`
- `0x180073a9c`
- `0x1800758bc`
- `0x180078b10`
- `0x18007e8ac`
- `0x18007ef54`
- `0x1800a5db8`
- `0x1800aa59c`
- `0x1800b015c`
- `0x1800b3dd4`
- `0x1800b948c`
- `0x1800b9670`
- `0x180100884`
- `0x18011a7f0`
- `0x18011a9a0`
- `0x18011aab0`
- `0x18011ab90`
- `0x18011bf90`
- `0x18011f4dc`
- `0x18011f6a0`
- `0x18011fa58`
- `0x18011fbe4`
- `0x18011fd88`
- `0x18011ff2c`
- `0x180120118`
- `0x18012034c`
- `0x180120478`
- `0x1801205dc`
- `0x1801207d0`
- `0x1801208c4`
- `0x180120aac`
- `0x180120bd8`
- `0x180120cec`
- `0x180120e14`
- `0x180120f6c`

## callees

- `0x18007efa0`
- `0x18007f054`
- `0x180262020`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007efde`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007efde`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18007f03b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18007f03b`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryA` at `0x18007efc6`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryA` at `0x18007efc6`

## string_xrefs

- `0x18007efbf`: `D3DDriverVerifier.dll`

## pseudocode

```c
void __fastcall CJournal::ReportDriverError(CJournal *this, int a2, const char *a3, __int64 a4)
{
  HMODULE LibraryA; // rax
  HMODULE v5; // rbx
  FARPROC ProcAddress; // rax
  CJournal *v7; // [rsp+40h] [rbp+8h] BYREF

  v7 = this;
  CJournal::RecordJournal((__int64)this, a2, (__int64)a3, a4, 0);
  LibraryA = LoadLibraryA("D3DDriverVerifier.dll");
  v5 = LibraryA;
  if ( LibraryA )
  {
    ProcAddress = GetProcAddress(LibraryA, "RetrieveVerifierInterface");
    if ( ProcAddress )
    {
      v7 = 0;
      ((void (__fastcall *)(GUID *, CJournal **))ProcAddress)(&IID_ID3DDriverVerifier1, &v7);
      if ( v7 )
      {
        (*(void (__fastcall **)(CJournal *, _QWORD, __int64))(*(_QWORD *)v7 + 64LL))(v7, 0, 1);
        (*(void (__fastcall **)(CJournal *))(*(_QWORD *)v7 + 16LL))(v7);
      }
    }
    FreeLibrary(v5);
  }
}

```

## disassembly

```asm
0x18007efa0  mov     [rsp+arg_8], rbx
0x18007efa5  mov     [rsp+arg_0], rcx
0x18007efaa  push    rdi
0x18007efab  sub     rsp, 30h
0x18007efaf  mov     rdi, r8
0x18007efb2  mov     dword ptr [rsp+38h+var_18], 0
0x18007efba  call    ?RecordJournal@CJournal@@QEAAXIPEBD_NW4RecordJournalOptions@@@Z; CJournal::RecordJournal(uint,char const *,bool,RecordJournalOptions)
0x18007efbf  lea     rcx, aD3ddriververif_1; "D3DDriverVerifier.dll"
0x18007efc6  call    cs:__imp_LoadLibraryA
0x18007efcc  mov     rbx, rax
0x18007efcf  test    rax, rax
0x18007efd2  jz      short loc_18007F041
0x18007efd4  lea     rdx, aRetrieveverifi; "RetrieveVerifierInterface"
0x18007efdb  mov     rcx, rax; hModule
0x18007efde  call    cs:__imp_GetProcAddress
0x18007efe4  test    rax, rax
0x18007efe7  jz      short loc_18007F038
0x18007efe9  lea     rdx, [rsp+38h+arg_0]
0x18007efee  mov     [rsp+38h+arg_0], 0
0x18007eff7  lea     rcx, IID_ID3DDriverVerifier1
0x18007effe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f003  mov     rcx, [rsp+38h+arg_0]
0x18007f008  test    rcx, rcx
0x18007f00b  jz      short loc_18007F038
0x18007f00d  mov     rax, [rcx]
0x18007f010  xor     r9d, r9d
0x18007f013  xor     edx, edx
0x18007f015  mov     [rsp+38h+var_18], rdi
0x18007f01a  mov     rax, [rax+40h]
0x18007f01e  lea     r8d, [r9+1]
0x18007f022  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f027  mov     rcx, [rsp+38h+arg_0]
0x18007f02c  mov     rax, [rcx]
0x18007f02f  mov     rax, [rax+10h]
0x18007f033  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f038  mov     rcx, rbx; hLibModule
0x18007f03b  call    cs:__imp_FreeLibrary
0x18007f041  mov     rbx, [rsp+38h+arg_8]
0x18007f046  add     rsp, 30h
0x18007f04a  pop     rdi
0x18007f04b  retn
```
