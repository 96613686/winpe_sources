# CLogStorage::_InitResidue(int)

- ea: `0x18000b798`
- end: `0x18000b96c`
- name: `?_InitResidue@CLogStorage@@AEAAXH@Z`
- size: `468`
- prototype: `void __fastcall(CLogStorage *__hidden this, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000a288`

## callees

- `0x18000b798`
- `0x18000b974`
- `0x18000d998`
- `0x18001266c`
- `0x18001280a`
- `0x180015010`

## string_xrefs

- `0x18000b902`: `com\complus\dtc\dtc\log\logmgr\src\logstor.cpp`
- `0x18000b93a`: `com\complus\dtc\dtc\log\logmgr\src\logstor.cpp`

## pseudocode

```c
void __fastcall CLogStorage::_InitResidue(CLogStorage *this, int a2)
{
  unsigned int *v2; // r15
  __int64 v4; // rsi
  struct CBuffer *v5; // rax
  unsigned int v6; // r8d
  _DWORD *v7; // rbp
  int v8; // eax
  int v9; // ebx
  BOOL v10; // r14d
  _DWORD *v11; // rdi
  int v12; // eax
  int v13; // edx
  BOOL v14; // eax
  unsigned int v15; // eax
  __int64 v16; // rax
  ulong pExceptionObject; // [rsp+70h] [rbp+8h] BYREF
  int v18; // [rsp+78h] [rbp+10h]

  v18 = a2;
  v2 = (unsigned int *)((char *)this + 40);
  v4 = (__int64)this;
  v5 = CLogStorage::_MapBuffer(this, 2 * *((_DWORD *)this + 10), *((_DWORD *)this + 10), 0, 0);
  v6 = *v2;
  *(_QWORD *)(v4 + 128) = v5;
  *(_QWORD *)(v4 + 136) = CLogStorage::_MapBuffer((CLogStorage *)v4, 3 * v6, v6, 0, 0);
  v7 = *(_DWORD **)(*(_QWORD *)(v4 + 128) + 24LL);
  if ( !v7 )
  {
    TraceFile(-2147024809, "E_INVALIDARG", "com\\complus\\dtc\\dtc\\log\\logmgr\\src\\logstor.cpp", 0x738u);
    pExceptionObject = -2147024809;
    throw &pExceptionObject;
  }
  v8 = ((__int64 (__fastcall *)(_QWORD, _DWORD *, void *))lpCalcCRC)(*v2 - 8, v7 + 2, pulCRCTable);
  v9 = 1;
  v10 = a2 && v8 == v7[1];
  v11 = *(_DWORD **)(*(_QWORD *)(v4 + 136) + 24LL);
  if ( !v11 )
  {
    TraceFile(-2147024809, "E_INVALIDARG", "com\\complus\\dtc\\dtc\\log\\logmgr\\src\\logstor.cpp", 0x75Au);
    pExceptionObject = -2147024809;
    throw &pExceptionObject;
  }
  v12 = ((__int64 (__fastcall *)(_QWORD, _DWORD *, void *))lpCalcCRC)(*v2 - 8, v11 + 2, pulCRCTable);
  v13 = v18;
  v14 = v18 && v12 == v11[1];
  if ( v10 && v14 )
  {
    v15 = v11[2];
    if ( v15 <= v7[2] )
    {
      if ( v15 >= v7[2] )
        v9 = *(_DWORD *)((char *)v7 + (unsigned int)v7[7] + 32) >= *(_DWORD *)((char *)v11 + (unsigned int)v11[7] + 32);
    }
    else
    {
      v9 = 0;
    }
    v16 = 120;
  }
  else
  {
    v9 = !v14;
    v16 = v4;
    v4 = 120;
  }
  *(_DWORD *)(v4 + v16) = v9;
  if ( !v13 )
  {
    memset_0(v7, 255, *v2);
    memset_0(v11, 255, *v2);
  }
}

```

## disassembly

```asm
0x18000b798  mov     [rsp+arg_10], rbx
0x18000b79d  mov     [rsp+arg_8], edx
0x18000b7a1  push    rbp
0x18000b7a2  push    rsi
0x18000b7a3  push    rdi
0x18000b7a4  push    r12
0x18000b7a6  push    r13
0x18000b7a8  push    r14
0x18000b7aa  push    r15
0x18000b7ac  sub     rsp, 30h
0x18000b7b0  lea     r15, [rcx+28h]
0x18000b7b4  mov     [rsp+68h+var_48], 0; unsigned int
0x18000b7bc  mov     r8d, [r15]; unsigned int
0x18000b7bf  mov     edi, edx
0x18000b7c1  xor     r9d, r9d; int
0x18000b7c4  mov     rsi, rcx
0x18000b7c7  lea     edx, [r8+r8]; unsigned int
0x18000b7cb  call    ?_MapBuffer@CLogStorage@@AEAAPEAVCBuffer@@KKHK@Z; CLogStorage::_MapBuffer(ulong,ulong,int,ulong)
0x18000b7d0  mov     r8d, [r15]; unsigned int
0x18000b7d3  xor     r9d, r9d; int
0x18000b7d6  mov     rcx, rsi; this
0x18000b7d9  mov     [rsi+80h], rax
0x18000b7e0  mov     [rsp+68h+var_48], 0; unsigned int
0x18000b7e8  lea     edx, [r8+r8*2]; unsigned int
0x18000b7ec  call    ?_MapBuffer@CLogStorage@@AEAAPEAVCBuffer@@KKHK@Z; CLogStorage::_MapBuffer(ulong,ulong,int,ulong)
0x18000b7f1  mov     [rsi+88h], rax
0x18000b7f8  mov     rax, [rsi+80h]
0x18000b7ff  mov     rbp, [rax+18h]
0x18000b803  test    rbp, rbp
0x18000b806  jz      loc_18000B8FC
0x18000b80c  mov     ecx, [r15]
0x18000b80f  lea     rdx, [rbp+8]
0x18000b813  mov     r8, cs:?pulCRCTable@@3PEAKEA; ulong * pulCRCTable
0x18000b81a  sub     ecx, 8
0x18000b81d  mov     rax, cs:?lpCalcCRC@@3P6AKIPEAEPEAK@ZEA; ulong (*lpCalcCRC)(uint,uchar *,ulong *)
0x18000b824  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b829  mov     ebx, 1
0x18000b82e  test    edi, edi
0x18000b830  jz      short loc_18000B83C
0x18000b832  cmp     eax, [rbp+4]
0x18000b835  jnz     short loc_18000B83C
0x18000b837  mov     r14d, ebx
0x18000b83a  jmp     short loc_18000B83F
0x18000b83c  xor     r14d, r14d
0x18000b83f  mov     rax, [rsi+88h]
0x18000b846  mov     rdi, [rax+18h]
0x18000b84a  test    rdi, rdi
0x18000b84d  jz      loc_18000B934
0x18000b853  mov     ecx, [r15]
0x18000b856  lea     rdx, [rdi+8]
0x18000b85a  mov     r8, cs:?pulCRCTable@@3PEAKEA; ulong * pulCRCTable
0x18000b861  sub     ecx, 8
0x18000b864  mov     rax, cs:?lpCalcCRC@@3P6AKIPEAEPEAK@ZEA; ulong (*lpCalcCRC)(uint,uchar *,ulong *)
0x18000b86b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b870  mov     edx, [rsp+68h+arg_8]
0x18000b874  test    edx, edx
0x18000b876  jz      short loc_18000B881
0x18000b878  cmp     eax, [rdi+4]
0x18000b87b  jnz     short loc_18000B881
0x18000b87d  mov     eax, ebx
0x18000b87f  jmp     short loc_18000B883
0x18000b881  xor     eax, eax
0x18000b883  test    r14d, r14d
0x18000b886  jz      short loc_18000B8B4
0x18000b888  test    eax, eax
0x18000b88a  jz      short loc_18000B8B4
0x18000b88c  mov     eax, [rdi+8]
0x18000b88f  cmp     eax, [rbp+8]
0x18000b892  jbe     short loc_18000B898
0x18000b894  xor     ebx, ebx
0x18000b896  jmp     short loc_18000B8AD
0x18000b898  jb      short loc_18000B8AD
0x18000b89a  mov     eax, [rdi+1Ch]
0x18000b89d  xor     ebx, ebx
0x18000b89f  mov     ecx, [rbp+1Ch]
0x18000b8a2  mov     eax, [rax+rdi+20h]
0x18000b8a6  cmp     [rcx+rbp+20h], eax
0x18000b8aa  setnb   bl
0x18000b8ad  mov     eax, 78h ; 'x'
0x18000b8b2  jmp     short loc_18000B8BE
0x18000b8b4  xor     ebx, eax
0x18000b8b6  mov     rax, rsi
0x18000b8b9  mov     esi, 78h ; 'x'
0x18000b8be  mov     [rsi+rax], ebx
0x18000b8c1  test    edx, edx
0x18000b8c3  jnz     short loc_18000B8E4
0x18000b8c5  mov     r8d, [r15]; Size
0x18000b8c8  mov     ebx, 0FFh
0x18000b8cd  mov     edx, ebx; Val
0x18000b8cf  mov     rcx, rbp; void *
0x18000b8d2  call    memset_0
0x18000b8d7  mov     r8d, [r15]; Size
0x18000b8da  mov     edx, ebx; Val
0x18000b8dc  mov     rcx, rdi; void *
0x18000b8df  call    memset_0
0x18000b8e4  mov     rbx, [rsp+68h+arg_10]
0x18000b8ec  add     rsp, 30h
0x18000b8f0  pop     r15
0x18000b8f2  pop     r14
0x18000b8f4  pop     r13
0x18000b8f6  pop     r12
0x18000b8f8  pop     rdi
0x18000b8f9  pop     rsi
0x18000b8fa  pop     rbp
0x18000b8fb  retn
0x18000b8fc  mov     r9d, 738h; unsigned int
0x18000b902  lea     r8, aComComplusDtcD_0; "com\\complus\\dtc\\dtc\\log\\logmgr\\sr"...
0x18000b909  lea     rdx, aEInvalidarg; "E_INVALIDARG"
0x18000b910  mov     ecx, 80070057h; int
0x18000b915  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x18000b91a  lea     rdx, _TI1K; pThrowInfo
0x18000b921  mov     [rsp+68h+pExceptionObject], 80070057h
0x18000b929  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x18000b92e  call    _CxxThrowException_0
0x18000b934  mov     r9d, 75Ah; unsigned int
0x18000b93a  lea     r8, aComComplusDtcD_0; "com\\complus\\dtc\\dtc\\log\\logmgr\\sr"...
0x18000b941  lea     rdx, aEInvalidarg; "E_INVALIDARG"
0x18000b948  mov     ecx, 80070057h; int
0x18000b94d  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x18000b952  lea     rdx, _TI1K; pThrowInfo
0x18000b959  mov     [rsp+68h+pExceptionObject], 80070057h
0x18000b961  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x18000b966  call    _CxxThrowException_0
```
