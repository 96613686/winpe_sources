# FindNextVolumePath(void *,unsigned __int64 *,ushort *)

- ea: `0x14001db30`
- end: `0x14001dc7e`
- name: `?FindNextVolumePath@@YAHPEAXPEA_KPEAG@Z`
- size: `334`
- prototype: `__int64 __fastcall(GUID *InterfaceClassGuid, unsigned __int64 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14001a530`

## callees

- `0x140008190`
- `0x14001c3b0`
- `0x14001db30`
- `0x14001dd54`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x14001db83`
- `KERNEL32!HeapAlloc` at `0x14001db83`
- `KERNEL32!HeapFree` at `0x14001dc46`
- `KERNEL32!HeapFree` at `0x14001dc46`
- `KERNEL32!GetProcessHeap` at `0x14001db4d`
- `KERNEL32!GetProcessHeap` at `0x14001db4d`
- `KERNEL32!SetLastError` at `0x14001db96`
- `KERNEL32!SetLastError` at `0x14001dc30`
- `KERNEL32!SetLastError` at `0x14001dc61`
- `KERNEL32!SetLastError` at `0x14001db96`
- `KERNEL32!SetLastError` at `0x14001dc30`
- `KERNEL32!SetLastError` at `0x14001dc61`
- `KERNEL32!GetLastError` at `0x14001db9c`
- `KERNEL32!GetLastError` at `0x14001dc36`
- `KERNEL32!GetLastError` at `0x14001db9c`
- `KERNEL32!GetLastError` at `0x14001dc36`

## pseudocode

```c
__int64 __fastcall FindNextVolumePath(GUID *InterfaceClassGuid, unsigned __int64 *a2, unsigned __int16 *a3)
{
  HANDLE ProcessHeap; // rax
  unsigned int Data1; // r12d
  int v8; // ebx
  void *v9; // r13
  unsigned __int16 *v10; // rbp
  unsigned int NextDevice; // edi
  DWORD LastError; // ebx
  int v13; // ecx
  int v14; // eax
  DWORD v15; // ecx
  int v16; // eax
  BOOL v17; // eax
  int v19; // [rsp+60h] [rbp+8h] BYREF
  unsigned __int64 v20; // [rsp+68h] [rbp+10h] BYREF

  ProcessHeap = GetProcessHeap();
  Data1 = InterfaceClassGuid[2].Data1;
  v8 = 0;
  v9 = ProcessHeap;
  v20 = 0;
  v19 = 0;
  if ( *a2 && a3 )
    *a3 = 0;
  v10 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 0, 0x10000u);
  if ( !v10 )
  {
    NextDevice = 0;
    SetLastError(8u);
    LastError = GetLastError();
    goto LABEL_21;
  }
  NextDevice = 1;
  while ( !v8 )
  {
    v20 = 0x8000;
    NextDevice = FindNextDevice(InterfaceClassGuid, &v20, v10);
    if ( !NextDevice )
      goto LABEL_19;
    NextDevice = FindVolume_IsVolumeOnDisk(Data1, v10, &v19);
    if ( !NextDevice )
      goto LABEL_19;
    v8 = v19;
  }
  if ( v20 <= *a2 )
  {
    v16 = StringCchCopyW(a3, *a2, v10);
    v15 = v16;
    if ( v16 >= 0 )
      goto LABEL_19;
    NextDevice = 0;
    if ( (v16 & 0x1FFF0000) == 0x70000 )
      v15 = (unsigned __int16)v16;
  }
  else
  {
    v13 = *(_DWORD *)InterfaceClassGuid[1].Data4;
    v14 = v13 - 1;
    if ( !v13 )
      v14 = 0;
    NextDevice = 0;
    *(_DWORD *)InterfaceClassGuid[1].Data4 = v14;
    v15 = 122;
  }
  SetLastError(v15);
LABEL_19:
  LastError = GetLastError();
  v17 = HeapFree(v9, 0, v10);
  if ( NextDevice )
  {
    NextDevice = v17;
    LastError = 6;
  }
LABEL_21:
  *a2 = v20;
  SetLastError(LastError);
  return NextDevice;
}

```

## disassembly

```asm
0x14001db30  mov     [rsp+arg_10], rbx
0x14001db35  push    rbp
0x14001db36  push    rsi
0x14001db37  push    rdi
0x14001db38  push    r12
0x14001db3a  push    r13
0x14001db3c  push    r14
0x14001db3e  push    r15
0x14001db40  sub     rsp, 20h
0x14001db44  mov     rsi, r8
0x14001db47  mov     r15, rdx
0x14001db4a  mov     r14, rcx
0x14001db4d  call    cs:__imp_GetProcessHeap
0x14001db53  mov     r12d, [r14+20h]
0x14001db57  xor     ebx, ebx
0x14001db59  mov     r13, rax
0x14001db5c  mov     [rsp+58h+arg_8], 0
0x14001db65  mov     [rsp+58h+arg_0], ebx
0x14001db69  cmp     [r15], rbx
0x14001db6c  jbe     short loc_14001DB78
0x14001db6e  test    rsi, rsi
0x14001db71  jz      short loc_14001DB78
0x14001db73  xor     ecx, ecx
0x14001db75  mov     [rsi], cx
0x14001db78  xor     edx, edx; dwFlags
0x14001db7a  mov     r8d, 10000h; dwBytes
0x14001db80  mov     rcx, r13; hHeap
0x14001db83  call    cs:__imp_HeapAlloc
0x14001db89  mov     rbp, rax
0x14001db8c  test    rax, rax
0x14001db8f  jnz     short loc_14001DBA9
0x14001db91  lea     ecx, [rax+8]; dwErrCode
0x14001db94  xor     edi, edi
0x14001db96  call    cs:__imp_SetLastError
0x14001db9c  call    cs:__imp_GetLastError
0x14001dba2  mov     ebx, eax
0x14001dba4  jmp     loc_14001DC57
0x14001dba9  mov     edi, 1
0x14001dbae  test    ebx, ebx
0x14001dbb0  jnz     short loc_14001DBED
0x14001dbb2  mov     r8, rbp; unsigned __int16 *
0x14001dbb5  mov     [rsp+58h+arg_8], 8000h
0x14001dbbe  lea     rdx, [rsp+58h+arg_8]; unsigned __int64 *
0x14001dbc3  mov     rcx, r14; InterfaceClassGuid
0x14001dbc6  call    ?FindNextDevice@@YAHPEAXPEA_KPEAG@Z; FindNextDevice(void *,unsigned __int64 *,ushort *)
0x14001dbcb  mov     edi, eax
0x14001dbcd  test    eax, eax
0x14001dbcf  jz      short loc_14001DC36
0x14001dbd1  lea     r8, [rsp+58h+arg_0]
0x14001dbd6  mov     rdx, rbp
0x14001dbd9  mov     ecx, r12d
0x14001dbdc  call    FindVolume_IsVolumeOnDisk
0x14001dbe1  mov     edi, eax
0x14001dbe3  test    eax, eax
0x14001dbe5  jz      short loc_14001DC36
0x14001dbe7  mov     ebx, [rsp+58h+arg_0]
0x14001dbeb  jmp     short loc_14001DBAE
0x14001dbed  mov     rdx, [r15]; unsigned __int64
0x14001dbf0  cmp     [rsp+58h+arg_8], rdx
0x14001dbf5  jbe     short loc_14001DC0E
0x14001dbf7  mov     ecx, [r14+18h]
0x14001dbfb  test    ecx, ecx
0x14001dbfd  lea     eax, [rcx-1]
0x14001dc00  cmovz   eax, ecx
0x14001dc03  xor     edi, edi
0x14001dc05  mov     [r14+18h], eax
0x14001dc09  lea     ecx, [rdi+7Ah]
0x14001dc0c  jmp     short loc_14001DC30
0x14001dc0e  mov     r8, rbp; unsigned __int16 *
0x14001dc11  mov     rcx, rsi; unsigned __int16 *
0x14001dc14  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14001dc19  mov     ecx, eax
0x14001dc1b  test    eax, eax
0x14001dc1d  jns     short loc_14001DC36
0x14001dc1f  xor     edi, edi
0x14001dc21  and     eax, 1FFF0000h
0x14001dc26  cmp     eax, 70000h
0x14001dc2b  jnz     short loc_14001DC30
0x14001dc2d  movzx   ecx, cx; dwErrCode
0x14001dc30  call    cs:__imp_SetLastError
0x14001dc36  call    cs:__imp_GetLastError
0x14001dc3c  mov     r8, rbp; lpMem
0x14001dc3f  xor     edx, edx; dwFlags
0x14001dc41  mov     rcx, r13; hHeap
0x14001dc44  mov     ebx, eax
0x14001dc46  call    cs:__imp_HeapFree
0x14001dc4c  test    edi, edi
0x14001dc4e  jz      short loc_14001DC57
0x14001dc50  mov     edi, eax
0x14001dc52  mov     ebx, 6
0x14001dc57  mov     rax, [rsp+58h+arg_8]
0x14001dc5c  mov     ecx, ebx; dwErrCode
0x14001dc5e  mov     [r15], rax
0x14001dc61  call    cs:__imp_SetLastError
0x14001dc67  mov     rbx, [rsp+58h+arg_10]
0x14001dc6c  mov     eax, edi
0x14001dc6e  add     rsp, 20h
0x14001dc72  pop     r15
0x14001dc74  pop     r14
0x14001dc76  pop     r13
0x14001dc78  pop     r12
0x14001dc7a  pop     rdi
0x14001dc7b  pop     rsi
0x14001dc7c  pop     rbp
0x14001dc7d  retn
```
