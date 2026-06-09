# MsiSIPRemoveSignedDataMsg(SIP_SUBJECTINFO_ *,ulong)

- ea: `0x18000ba20`
- end: `0x18000bb9c`
- name: `?MsiSIPRemoveSignedDataMsg@@YAHPEAUSIP_SUBJECTINFO_@@K@Z`
- size: `380`
- prototype: `__int64 __fastcall(struct SIP_SUBJECTINFO_ *, int)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180001190`
- `0x180003340`
- `0x180005ea0`
- `0x180005f00`
- `0x180006690`
- `0x180006ee4`
- `0x18000ba20`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18000ba8e`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18000bb3d`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18000ba8e`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18000bb3d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ba83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000baab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bb1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ba83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000baab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bb1a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000bb12`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000bb49`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000bb60`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000bb84`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000bb12`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000bb49`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000bb60`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000bb84`
- `api-ms-win-core-kernel32-legacy-l1-1-0!LoadLibraryW` at `0x18000ba60`
- `api-ms-win-core-kernel32-legacy-l1-1-0!LoadLibraryW` at `0x18000ba60`

## string_xrefs

- `0x18000ba59`: `ole32.dll`

## pseudocode

```c
__int64 __fastcall MsiSIPRemoveSignedDataMsg(struct SIP_SUBJECTINFO_ *a1, int a2)
{
  HMODULE LibraryW; // rax
  HMODULE v4; // rdi
  DWORD LastError; // ebx
  DWORD v6; // ecx
  unsigned int v7; // esi
  struct IStorage *StorageFromSubject; // rax
  struct IStorage *v9; // rbx
  int v10; // eax
  DWORD v11; // ebx
  bool v13; // [rsp+40h] [rbp+8h] BYREF
  struct IStorage *v14; // [rsp+50h] [rbp+18h] BYREF

  v13 = 0;
  if ( !a1 || a2 || a1->cbSize < 0x58 )
  {
    v6 = 87;
    goto LABEL_21;
  }
  LibraryW = LoadLibraryW(L"ole32.dll");
  v4 = LibraryW;
  if ( !LibraryW )
    return 0;
  if ( !(unsigned int)MyCoInitialize(LibraryW, &v13) )
  {
    LastError = GetLastError();
LABEL_7:
    FreeLibrary(v4);
    v6 = LastError;
LABEL_21:
    SetLastError(v6);
    return 0;
  }
  if ( !(unsigned int)VerifySubjectGUID(v4, a1->pgSubjectType) )
  {
    LastError = GetLastError();
    MyCoUninitialize(v4, v13);
    goto LABEL_7;
  }
  v7 = 1;
  StorageFromSubject = GetStorageFromSubject(a1, 0x10022u, v4, 1);
  v9 = StorageFromSubject;
  v14 = StorageFromSubject;
  if ( StorageFromSubject )
  {
    v10 = ((__int64 (__fastcall *)(struct IStorage *, __int64 *))StorageFromSubject->lpVtbl->DestroyElement)(
            StorageFromSubject,
            qword_18000F930);
    if ( (int)(v10 + 0x80000000) < 0 || v10 == -2147287038 )
    {
      SetLastError(0);
      if ( ((int (__fastcall *)(struct IStorage *, __int64))v9->lpVtbl->Commit)(v9, 1) >= 0 )
      {
        v11 = 0;
        goto LABEL_15;
      }
    }
    else
    {
      SetLastError(0xBu);
    }
  }
  v7 = 0;
  v11 = GetLastError();
LABEL_15:
  CComPointer<IStorage>::operator=(&v14, 0);
  MyCoUninitialize(v4, v13);
  FreeLibrary(v4);
  if ( v11 )
    SetLastError(v11);
  CComPointer<IStream>::~CComPointer<IStream>(&v14);
  return v7;
}

```

## disassembly

```asm
0x18000ba20  mov     rax, rsp
0x18000ba23  push    rdi
0x18000ba24  sub     rsp, 30h
0x18000ba28  mov     qword ptr [rax-18h], 0FFFFFFFFFFFFFFFEh
0x18000ba30  mov     [rax+10h], rbx
0x18000ba34  mov     [rax+20h], rsi
0x18000ba38  mov     rbx, rcx
0x18000ba3b  mov     byte ptr [rax+8], 0
0x18000ba3f  test    rcx, rcx
0x18000ba42  jz      loc_18000BB7F
0x18000ba48  test    edx, edx
0x18000ba4a  jnz     loc_18000BB7F
0x18000ba50  cmp     dword ptr [rcx], 58h ; 'X'
0x18000ba53  jb      loc_18000BB7F
0x18000ba59  lea     rcx, LibFileName; "ole32.dll"
0x18000ba60  call    cs:__imp_LoadLibraryW
0x18000ba66  mov     rdi, rax
0x18000ba69  test    rax, rax
0x18000ba6c  jz      loc_18000BB8A
0x18000ba72  lea     rdx, [rsp+38h+arg_0]; bool *
0x18000ba77  mov     rcx, rax; HINSTANCE
0x18000ba7a  call    ?MyCoInitialize@@YAHPEAUHINSTANCE__@@PEA_N@Z; MyCoInitialize(HINSTANCE__ *,bool *)
0x18000ba7f  test    eax, eax
0x18000ba81  jnz     short loc_18000BA9B
0x18000ba83  call    cs:__imp_GetLastError
0x18000ba89  mov     ebx, eax
0x18000ba8b  mov     rcx, rdi; hLibModule
0x18000ba8e  call    cs:__imp_FreeLibrary
0x18000ba94  mov     ecx, ebx
0x18000ba96  jmp     loc_18000BB84
0x18000ba9b  mov     rdx, [rbx+8]; struct _GUID *
0x18000ba9f  mov     rcx, rdi; HINSTANCE
0x18000baa2  call    ?VerifySubjectGUID@@YAHPEAUHINSTANCE__@@PEAU_GUID@@@Z; VerifySubjectGUID(HINSTANCE__ *,_GUID *)
0x18000baa7  test    eax, eax
0x18000baa9  jnz     short loc_18000BAC1
0x18000baab  call    cs:__imp_GetLastError
0x18000bab1  mov     ebx, eax
0x18000bab3  mov     dl, [rsp+38h+arg_0]; bool
0x18000bab7  mov     rcx, rdi; HINSTANCE
0x18000baba  call    ?MyCoUninitialize@@YAXPEAUHINSTANCE__@@_N@Z; MyCoUninitialize(HINSTANCE__ *,bool)
0x18000babf  jmp     short loc_18000BA8B
0x18000bac1  mov     esi, 1
0x18000bac6  mov     r9b, sil; bool
0x18000bac9  mov     r8, rdi; HINSTANCE
0x18000bacc  mov     edx, 10022h; unsigned int
0x18000bad1  mov     rcx, rbx; struct SIP_SUBJECTINFO_ *
0x18000bad4  call    ?GetStorageFromSubject@@YAPEAUIStorage@@PEAUSIP_SUBJECTINFO_@@KPEAUHINSTANCE__@@_N@Z; GetStorageFromSubject(SIP_SUBJECTINFO_ *,ulong,HINSTANCE__ *,bool)
0x18000bad9  mov     rbx, rax
0x18000badc  mov     [rsp+38h+arg_10], rax
0x18000bae1  test    rax, rax
0x18000bae4  jz      short loc_18000BB18
0x18000bae6  mov     rcx, [rax]
0x18000bae9  mov     rax, [rcx+60h]
0x18000baed  lea     rdx, qword_18000F930
0x18000baf4  mov     rcx, rbx
0x18000baf7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bafc  mov     edx, 80000000h
0x18000bb01  lea     ecx, [rax+rdx]
0x18000bb04  test    edx, ecx
0x18000bb06  jnz     short loc_18000BB5E
0x18000bb08  cmp     eax, 80030002h
0x18000bb0d  jz      short loc_18000BB5E
0x18000bb0f  lea     ecx, [rsi+0Ah]; dwErrCode
0x18000bb12  call    cs:__imp_SetLastError
0x18000bb18  xor     esi, esi
0x18000bb1a  call    cs:__imp_GetLastError
0x18000bb20  mov     ebx, eax
0x18000bb22  xor     edx, edx
0x18000bb24  lea     rcx, [rsp+38h+arg_10]
0x18000bb29  call    ??4?$CComPointer@UIStorage@@@@QEAAAEAV0@PEAUIStorage@@@Z; CComPointer<IStorage>::operator=(IStorage *)
0x18000bb2e  mov     dl, [rsp+38h+arg_0]; bool
0x18000bb32  mov     rcx, rdi; HINSTANCE
0x18000bb35  call    ?MyCoUninitialize@@YAXPEAUHINSTANCE__@@_N@Z; MyCoUninitialize(HINSTANCE__ *,bool)
0x18000bb3a  mov     rcx, rdi; hLibModule
0x18000bb3d  call    cs:__imp_FreeLibrary
0x18000bb43  test    ebx, ebx
0x18000bb45  jz      short loc_18000BB50
0x18000bb47  mov     ecx, ebx; dwErrCode
0x18000bb49  call    cs:__imp_SetLastError
0x18000bb4f  nop
0x18000bb50  lea     rcx, [rsp+38h+arg_10]
0x18000bb55  call    ??1?$CComPointer@UIStream@@@@QEAA@XZ; CComPointer<IStream>::~CComPointer<IStream>(void)
0x18000bb5a  mov     eax, esi
0x18000bb5c  jmp     short loc_18000BB8C
0x18000bb5e  xor     ecx, ecx; dwErrCode
0x18000bb60  call    cs:__imp_SetLastError
0x18000bb66  mov     rax, [rbx]
0x18000bb69  mov     edx, esi
0x18000bb6b  mov     rcx, rbx
0x18000bb6e  mov     rax, [rax+48h]
0x18000bb72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bb77  test    eax, eax
0x18000bb79  js      short loc_18000BB18
0x18000bb7b  xor     ebx, ebx
0x18000bb7d  jmp     short loc_18000BB22
0x18000bb7f  mov     ecx, 57h ; 'W'; dwErrCode
0x18000bb84  call    cs:__imp_SetLastError
0x18000bb8a  xor     eax, eax
0x18000bb8c  mov     rbx, [rsp+38h+arg_8]
0x18000bb91  mov     rsi, [rsp+38h+arg_18]
0x18000bb96  add     rsp, 30h
0x18000bb9a  pop     rdi
0x18000bb9b  retn
```
