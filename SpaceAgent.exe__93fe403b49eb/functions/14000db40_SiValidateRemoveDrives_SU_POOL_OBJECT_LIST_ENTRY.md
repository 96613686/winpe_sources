# SiValidateRemoveDrives(_SU_POOL_OBJECT *,_LIST_ENTRY *)

- ea: `0x14000db40`
- end: `0x14000dbed`
- name: `?SiValidateRemoveDrives@@YAHPEAU_SU_POOL_OBJECT@@PEAU_LIST_ENTRY@@@Z`
- size: `173`
- prototype: `__int64 __fastcall(struct _SU_POOL_OBJECT *, struct _LIST_ENTRY *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x14000ee10`
- `0x140019310`

## callees

- `0x14000db40`
- `0x14000e298`
- `0x140012bd0`

## import_xrefs

- `KERNEL32!LocalFree` at `0x14000dbd2`
- `KERNEL32!LocalFree` at `0x14000dbd2`
- `KERNEL32!SetLastError` at `0x14000db9b`
- `KERNEL32!SetLastError` at `0x14000dbc2`
- `KERNEL32!SetLastError` at `0x14000db9b`
- `KERNEL32!SetLastError` at `0x14000dbc2`

## pseudocode

```c
__int64 __fastcall SiValidateRemoveDrives(struct _SU_POOL_OBJECT *a1, struct _LIST_ENTRY *a2)
{
  int (*v4)(void *, void *, void *, void *, void *); // rdx
  unsigned int NumberOfDrives; // ebx
  void *v6; // r9
  struct _LIST_ENTRY *Flink; // rax
  unsigned int v8; // edi
  unsigned int v9; // esi
  struct _SU_SPACE_OBJECT *v10; // rbp
  void *v12; // [rsp+20h] [rbp-28h]
  void *v13; // [rsp+28h] [rbp-20h]
  unsigned int v14; // [rsp+50h] [rbp+8h] BYREF
  unsigned int v15; // [rsp+60h] [rbp+18h] BYREF

  v14 = 0;
  v15 = 0;
  NumberOfDrives = SuGetNumberOfDrives((struct _GUID *)((char *)a1 + 40), &v14);
  if ( NumberOfDrives )
  {
    Flink = a2->Flink;
    v8 = 0;
    v9 = v14;
    if ( a2->Flink == a2 )
      goto LABEL_6;
    do
    {
      Flink = Flink->Flink;
      ++v8;
    }
    while ( Flink != a2 );
    if ( v8 <= v14 )
    {
LABEL_6:
      v10 = SuEnumerateSpaces(a1, v4, &v15, v6, v12, v13);
      if ( v9 - v8 < v15 )
      {
        SetLastError(0x80E7000B);
        NumberOfDrives = 0;
      }
      if ( v10 )
        LocalFree(v10);
    }
    else
    {
      SetLastError(0x57u);
      return 0;
    }
  }
  return NumberOfDrives;
}

```

## disassembly

```asm
0x14000db40  mov     rax, rsp
0x14000db43  mov     [rax+10h], rbx
0x14000db47  mov     [rax+20h], rbp
0x14000db4b  push    rsi
0x14000db4c  push    rdi
0x14000db4d  push    r14
0x14000db4f  sub     rsp, 30h
0x14000db53  mov     r14, rdx
0x14000db56  mov     dword ptr [rax+8], 0
0x14000db5d  mov     rbp, rcx
0x14000db60  mov     dword ptr [rax+18h], 0
0x14000db67  add     rcx, 28h ; '('; struct _GUID *
0x14000db6b  lea     rdx, [rax+8]; unsigned int *
0x14000db6f  call    ?SuGetNumberOfDrives@@YAHPEAU_GUID@@PEAK@Z; SuGetNumberOfDrives(_GUID *,ulong *)
0x14000db74  mov     ebx, eax
0x14000db76  test    eax, eax
0x14000db78  jz      short loc_14000DBD8
0x14000db7a  mov     rax, [r14]
0x14000db7d  xor     edi, edi
0x14000db7f  mov     esi, [rsp+48h+arg_0]
0x14000db83  cmp     rax, r14
0x14000db86  jz      short loc_14000DBA5
0x14000db88  mov     rax, [rax]
0x14000db8b  inc     edi
0x14000db8d  cmp     rax, r14
0x14000db90  jnz     short loc_14000DB88
0x14000db92  cmp     edi, esi
0x14000db94  jbe     short loc_14000DBA5
0x14000db96  mov     ecx, 57h ; 'W'; dwErrCode
0x14000db9b  call    cs:__imp_SetLastError
0x14000dba1  xor     ebx, ebx
0x14000dba3  jmp     short loc_14000DBD8
0x14000dba5  lea     r8, [rsp+48h+arg_10]; void *
0x14000dbaa  mov     rcx, rbp; struct _SU_POOL_OBJECT *
0x14000dbad  call    ?SuEnumerateSpaces@@YAPEAU_SU_SPACE_OBJECT@@PEAU_SU_POOL_OBJECT@@P6AHPEAX1111@Z1111@Z; SuEnumerateSpaces(_SU_POOL_OBJECT *,int (*)(void *,void *,void *,void *,void *),void *,void *,void *,void *)
0x14000dbb2  sub     esi, edi
0x14000dbb4  mov     rbp, rax
0x14000dbb7  cmp     esi, [rsp+48h+arg_10]
0x14000dbbb  jnb     short loc_14000DBCA
0x14000dbbd  mov     ecx, 80E7000Bh; dwErrCode
0x14000dbc2  call    cs:__imp_SetLastError
0x14000dbc8  xor     ebx, ebx
0x14000dbca  test    rbp, rbp
0x14000dbcd  jz      short loc_14000DBD8
0x14000dbcf  mov     rcx, rbp; hMem
0x14000dbd2  call    cs:__imp_LocalFree
0x14000dbd8  mov     rbp, [rsp+48h+arg_18]
0x14000dbdd  mov     eax, ebx
0x14000dbdf  mov     rbx, [rsp+48h+arg_8]
0x14000dbe4  add     rsp, 30h
0x14000dbe8  pop     r14
0x14000dbea  pop     rdi
0x14000dbeb  pop     rsi
0x14000dbec  retn
```
