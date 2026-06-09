# ABO_WRAPPER::CloseKey(ulong)

- ea: `0x18000be60`
- end: `0x18000beeb`
- name: `?CloseKey@ABO_WRAPPER@@UEAAJK@Z`
- size: `139`
- prototype: `__int64 __fastcall(ABO_WRAPPER *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180001f90`
- `0x180003f14`
- `0x180007a80`
- `0x18000be60`
- `0x18000f65c`

## import_xrefs

- `iisutil!?DeleteKey@CLKRHashTable@@QEAA?AW4LK_RETCODE@@_K@Z` at `0x18000bec1`
- `iisutil!?DeleteKey@CLKRHashTable@@QEAA?AW4LK_RETCODE@@_K@Z` at `0x18000bec1`

## pseudocode

```c
__int64 __fastcall ABO_WRAPPER::CloseKey(ABO_WRAPPER *this, unsigned int a2)
{
  unsigned int v2; // ebx
  __int64 v3; // rdi
  char *v4; // rbp
  HANDLE_ENTRY *v6; // [rsp+40h] [rbp+18h] BYREF

  v2 = 0;
  v3 = a2;
  v6 = 0;
  if ( a2 )
  {
    v4 = (char *)this + 48;
    if ( (unsigned int)CTypedHashTable<HANDLE_TABLE,HANDLE_ENTRY,unsigned long,CLKRHashTable>::FindKey(
                         (char *)this + 48,
                         a2,
                         &v6) )
    {
      ABO_MAPPER_LOG::WriteLogEntry((HANDLE *)g_pAboLog, L"Could not Find Entry for Handle (%X)", (unsigned int)v3);
      v2 = -2147024890;
    }
    else
    {
      v2 = HANDLE_ENTRY::Close(v6);
      CLKRHashTable::DeleteKey(v4, v3);
    }
    if ( v6 )
      HANDLE_ENTRY::DereferenceHandleEntry(v6);
  }
  return v2;
}

```

## disassembly

```asm
0x18000be60  mov     rax, rsp
0x18000be63  mov     [rax+8], rbx
0x18000be67  mov     [rax+10h], rbp
0x18000be6b  push    rdi
0x18000be6c  sub     rsp, 20h
0x18000be70  xor     ebx, ebx
0x18000be72  mov     edi, edx
0x18000be74  mov     [rax+18h], rbx
0x18000be78  test    edx, edx
0x18000be7a  jz      short loc_18000BED9
0x18000be7c  lea     rbp, [rcx+30h]
0x18000be80  mov     edx, edi
0x18000be82  mov     rcx, rbp
0x18000be85  lea     r8, [rax+18h]
0x18000be89  call    ?FindKey@?$CTypedHashTable@VHANDLE_TABLE@@VHANDLE_ENTRY@@KVCLKRHashTable@@@@QEBA?AW4LK_RETCODE@@KPEAPEAVHANDLE_ENTRY@@@Z; CTypedHashTable<HANDLE_TABLE,HANDLE_ENTRY,ulong,CLKRHashTable>::FindKey(ulong,HANDLE_ENTRY * *)
0x18000be8e  test    eax, eax
0x18000be90  jz      short loc_18000BEAF
0x18000be92  mov     rcx, cs:?g_pAboLog@@3PEAVABO_MAPPER_LOG@@EA; this
0x18000be99  lea     rdx, aCouldNotFindEn; "Could not Find Entry for Handle (%X)"
0x18000bea0  mov     r8d, edi
0x18000bea3  call    ?WriteLogEntry@ABO_MAPPER_LOG@@QEAAJPEBGZZ; ABO_MAPPER_LOG::WriteLogEntry(ushort const *,...)
0x18000bea8  mov     ebx, 80070006h
0x18000bead  jmp     short loc_18000BEC7
0x18000beaf  mov     rcx, [rsp+28h+arg_10]; this
0x18000beb4  call    ?Close@HANDLE_ENTRY@@QEAAJXZ; HANDLE_ENTRY::Close(void)
0x18000beb9  mov     rdx, rdi
0x18000bebc  mov     rcx, rbp
0x18000bebf  mov     ebx, eax
0x18000bec1  call    cs:__imp_?DeleteKey@CLKRHashTable@@QEAA?AW4LK_RETCODE@@_K@Z; CLKRHashTable::DeleteKey(unsigned __int64)
0x18000bec7  cmp     [rsp+28h+arg_10], 0
0x18000becd  jz      short loc_18000BED9
0x18000becf  mov     rcx, [rsp+28h+arg_10]; this
0x18000bed4  call    ?DereferenceHandleEntry@HANDLE_ENTRY@@QEAAXXZ; HANDLE_ENTRY::DereferenceHandleEntry(void)
0x18000bed9  mov     rbp, [rsp+28h+arg_8]
0x18000bede  mov     eax, ebx
0x18000bee0  mov     rbx, [rsp+28h+arg_0]
0x18000bee5  add     rsp, 20h
0x18000bee9  pop     rdi
0x18000beea  retn
```
