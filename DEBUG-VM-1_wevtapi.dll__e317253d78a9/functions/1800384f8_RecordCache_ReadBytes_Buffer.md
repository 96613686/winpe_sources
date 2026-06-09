# RecordCache::ReadBytes(Buffer &)

- ea: `0x1800384f8`
- end: `0x1800385e4`
- name: `?ReadBytes@RecordCache@@IEAAKAEAVBuffer@@@Z`
- size: `236`
- prototype: `unsigned int __fastcall(RecordCache *__hidden this, struct Buffer *)`
- caller_count: `5`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x1800377b8`
- `0x180037cbc`
- `0x180037da8`
- `0x18003872c`
- `0x18003882c`

## callees

- `0x180009d80`
- `0x180023548`
- `0x1800373fc`
- `0x1800384f8`
- `0x180038fb4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038537`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038537`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180038529`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180038529`

## pseudocode

```c
__int64 __fastcall RecordCache::ReadBytes(HANDLE *this, struct Buffer *a2)
{
  DWORD v2; // r8d
  DWORD LastError; // ebx
  __int128 pExceptionObject; // [rsp+30h] [rbp-38h] BYREF
  __int64 v8; // [rsp+40h] [rbp-28h]
  DWORD v9; // [rsp+48h] [rbp-20h]
  int v10; // [rsp+4Ch] [rbp-1Ch]
  int v11; // [rsp+50h] [rbp-18h]
  unsigned int v12; // [rsp+70h] [rbp+8h] BYREF

  v2 = *((_DWORD *)a2 + 4);
  v12 = 0;
  if ( !ReadFile(this[7], *((LPVOID *)a2 + 1), v2, &v12, 0) )
  {
    LastError = GetLastError();
    if ( !LastError )
      LastError = 1287;
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_ed4ad13171c934ad5ef7c6740982dc1b_Traceguids, LastError);
    }
    v8 = 0;
    v9 = LastError;
    v10 = -1;
    pExceptionObject = 0;
    v11 = 358;
    throw (EvtException *)&pExceptionObject;
  }
  if ( *((_DWORD *)a2 + 4) > v12 )
    Buffer::SetCurrentIndex(a2, v12);
  this[2] = (HANDLE)RecordCache::GetFilePosition((RecordCache *)this);
  return v12;
}

```

## disassembly

```asm
0x1800384f8  mov     rax, rsp
0x1800384fb  mov     [rax+10h], rbx
0x1800384ff  push    rdi
0x180038500  sub     rsp, 60h
0x180038504  mov     r8d, [rdx+10h]; nNumberOfBytesToRead
0x180038508  lea     r9, [rax+8]; lpNumberOfBytesRead
0x18003850c  mov     rbx, rdx
0x18003850f  mov     dword ptr [rax+8], 0
0x180038516  mov     rdx, [rdx+8]; lpBuffer
0x18003851a  mov     rdi, rcx
0x18003851d  mov     rcx, [rcx+38h]; hFile
0x180038521  mov     qword ptr [rax-48h], 0
0x180038529  call    cs:__imp_ReadFile
0x18003852f  test    eax, eax
0x180038531  jnz     loc_1800385B8
0x180038537  call    cs:__imp_GetLastError
0x18003853d  mov     ebx, eax
0x18003853f  mov     eax, 507h
0x180038544  test    ebx, ebx
0x180038546  cmovz   ebx, eax
0x180038549  mov     rcx, cs:WPP_GLOBAL_Control
0x180038550  lea     rax, WPP_GLOBAL_Control
0x180038557  cmp     rcx, rax
0x18003855a  jz      short loc_180038580
0x18003855c  test    byte ptr [rcx+1Ch], 1
0x180038560  jz      short loc_180038580
0x180038562  cmp     byte ptr [rcx+19h], 2
0x180038566  jb      short loc_180038580
0x180038568  mov     rcx, [rcx+10h]
0x18003856c  lea     r8, WPP_ed4ad13171c934ad5ef7c6740982dc1b_Traceguids
0x180038573  mov     edx, 10h
0x180038578  mov     r9d, ebx
0x18003857b  call    WPP_SF_D
0x180038580  xorps   xmm0, xmm0
0x180038583  mov     [rsp+68h+var_28], 0
0x18003858c  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180038593  mov     [rsp+68h+var_20], ebx
0x180038597  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x18003859c  mov     [rsp+68h+var_1C], 0FFFFFFFFh
0x1800385a4  movdqu  [rsp+68h+pExceptionObject], xmm0
0x1800385aa  mov     [rsp+68h+var_18], 166h
0x1800385b2  call    _CxxThrowException_0
0x1800385b8  mov     edx, [rsp+68h+arg_0]; unsigned int
0x1800385bc  cmp     [rbx+10h], edx
0x1800385bf  jbe     short loc_1800385C9
0x1800385c1  mov     rcx, rbx; this
0x1800385c4  call    ?SetCurrentIndex@Buffer@@UEAAXK@Z; Buffer::SetCurrentIndex(ulong)
0x1800385c9  mov     rcx, rdi; this
0x1800385cc  call    ?GetFilePosition@RecordCache@@QEAA_KXZ; RecordCache::GetFilePosition(void)
0x1800385d1  mov     rbx, [rsp+68h+arg_8]
0x1800385d6  mov     [rdi+10h], rax
0x1800385da  mov     eax, [rsp+68h+arg_0]
0x1800385de  add     rsp, 60h
0x1800385e2  pop     rdi
0x1800385e3  retn
```
