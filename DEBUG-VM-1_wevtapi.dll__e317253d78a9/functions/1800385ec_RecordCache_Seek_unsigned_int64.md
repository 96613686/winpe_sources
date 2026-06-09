# RecordCache::Seek(unsigned __int64)

- ea: `0x1800385ec`
- end: `0x180038724`
- name: `?Seek@RecordCache@@IEAAX_K@Z`
- size: `312`
- prototype: `void __fastcall(RecordCache *__hidden this, unsigned __int64)`
- caller_count: `5`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1800377b8`
- `0x180037cbc`
- `0x180037da8`
- `0x18003872c`
- `0x18003882c`

## callees

- `0x180023548`
- `0x1800373fc`
- `0x1800385ec`
- `0x180038fb4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038692`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038692`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180038688`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180038688`

## pseudocode

```c
void __fastcall RecordCache::Seek(RecordCache *this, unsigned __int64 a2)
{
  DWORD LastError; // ebx
  __int128 pExceptionObject; // [rsp+20h] [rbp-30h] BYREF
  __int64 v5; // [rsp+30h] [rbp-20h]
  int v6; // [rsp+38h] [rbp-18h]
  int v7; // [rsp+3Ch] [rbp-14h]
  int v8; // [rsp+40h] [rbp-10h]
  union _LARGE_INTEGER NewFilePointer; // [rsp+60h] [rbp+10h] BYREF

  NewFilePointer.QuadPart = 0;
  if ( a2 > *((_QWORD *)this + 1) )
  {
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_ed4ad13171c934ad5ef7c6740982dc1b_Traceguids, 13);
    }
    v5 = 0;
    v6 = 13;
    v7 = -1;
    pExceptionObject = 0;
    v8 = 394;
    throw (EvtException *)&pExceptionObject;
  }
  if ( !SetFilePointerEx(*((HANDLE *)this + 7), (LARGE_INTEGER)(*((_QWORD *)this + 122) + a2), &NewFilePointer, 0) )
  {
    LastError = GetLastError();
    if ( !LastError )
      LastError = 1287;
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_ed4ad13171c934ad5ef7c6740982dc1b_Traceguids, LastError);
    }
    v5 = 0;
    v6 = LastError;
    v7 = -1;
    pExceptionObject = 0;
    v8 = 403;
    throw (EvtException *)&pExceptionObject;
  }
  *((_QWORD *)this + 2) = RecordCache::GetFilePosition(this);
}

```

## disassembly

```asm
0x1800385ec  mov     [rsp-8+arg_8], rbx
0x1800385f1  push    rbp
0x1800385f2  mov     rbp, rsp
0x1800385f5  sub     rsp, 50h
0x1800385f9  mov     rbx, rcx
0x1800385fc  mov     qword ptr [rbp+NewFilePointer], 0
0x180038604  cmp     rdx, [rcx+8]
0x180038608  jbe     short loc_180038676
0x18003860a  mov     rcx, cs:WPP_GLOBAL_Control
0x180038611  lea     rax, WPP_GLOBAL_Control
0x180038618  mov     ebx, 0Dh
0x18003861d  cmp     rcx, rax
0x180038620  jz      short loc_180038644
0x180038622  test    byte ptr [rcx+1Ch], 1
0x180038626  jz      short loc_180038644
0x180038628  cmp     byte ptr [rcx+19h], 2
0x18003862c  jb      short loc_180038644
0x18003862e  mov     rcx, [rcx+10h]
0x180038632  lea     edx, [rbx+5]
0x180038635  mov     r9d, ebx
0x180038638  lea     r8, WPP_ed4ad13171c934ad5ef7c6740982dc1b_Traceguids
0x18003863f  call    WPP_SF_D
0x180038644  xorps   xmm0, xmm0
0x180038647  mov     [rbp+var_20], 0
0x18003864f  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180038656  mov     [rbp+var_18], ebx
0x180038659  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18003865d  mov     [rbp+var_14], 0FFFFFFFFh
0x180038664  movdqu  [rbp+pExceptionObject], xmm0
0x180038669  mov     [rbp+var_10], 18Ah
0x180038670  call    _CxxThrowException_0
0x180038676  add     rdx, [rcx+3D0h]; liDistanceToMove
0x18003867d  lea     r8, [rbp+NewFilePointer]; lpNewFilePointer
0x180038681  mov     rcx, [rcx+38h]; hFile
0x180038685  xor     r9d, r9d; dwMoveMethod
0x180038688  call    cs:__imp_SetFilePointerEx
0x18003868e  test    eax, eax
0x180038690  jnz     short loc_18003870D
0x180038692  call    cs:__imp_GetLastError
0x180038698  mov     ebx, eax
0x18003869a  mov     eax, 507h
0x18003869f  test    ebx, ebx
0x1800386a1  cmovz   ebx, eax
0x1800386a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800386ab  lea     rax, WPP_GLOBAL_Control
0x1800386b2  cmp     rcx, rax
0x1800386b5  jz      short loc_1800386DB
0x1800386b7  test    byte ptr [rcx+1Ch], 1
0x1800386bb  jz      short loc_1800386DB
0x1800386bd  cmp     byte ptr [rcx+19h], 2
0x1800386c1  jb      short loc_1800386DB
0x1800386c3  mov     rcx, [rcx+10h]
0x1800386c7  lea     r8, WPP_ed4ad13171c934ad5ef7c6740982dc1b_Traceguids
0x1800386ce  mov     edx, 13h
0x1800386d3  mov     r9d, ebx
0x1800386d6  call    WPP_SF_D
0x1800386db  xorps   xmm0, xmm0
0x1800386de  mov     [rbp+var_20], 0
0x1800386e6  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1800386ed  mov     [rbp+var_18], ebx
0x1800386f0  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800386f4  mov     [rbp+var_14], 0FFFFFFFFh
0x1800386fb  movdqu  [rbp+pExceptionObject], xmm0
0x180038700  mov     [rbp+var_10], 193h
0x180038707  call    _CxxThrowException_0
0x18003870d  mov     rcx, rbx; this
0x180038710  call    ?GetFilePosition@RecordCache@@QEAA_KXZ; RecordCache::GetFilePosition(void)
0x180038715  mov     [rbx+10h], rax
0x180038719  mov     rbx, [rsp+50h+arg_8]
0x18003871e  add     rsp, 50h
0x180038722  pop     rbp
0x180038723  retn
```
