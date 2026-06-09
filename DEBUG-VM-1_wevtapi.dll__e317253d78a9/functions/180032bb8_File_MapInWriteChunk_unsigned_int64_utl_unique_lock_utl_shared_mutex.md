# File::MapInWriteChunk(unsigned __int64,utl::unique_lock<utl::shared_mutex> &)

- ea: `0x180032bb8`
- end: `0x180032ee1`
- name: `?MapInWriteChunk@File@@AEAAX_KAEAV?$unique_lock@Vshared_mutex@utl@@@utl@@@Z`
- size: `809`
- prototype: `__int64 __fastcall(File *this, unsigned __int64)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18003409c`

## callees

- `0x18000e838`
- `0x180023548`
- `0x1800249f0`
- `0x1800254b4`
- `0x180031d9c`
- `0x180032bb8`
- `0x180033b04`
- `0x180033cec`
- `0x180034b18`
- `0x180034ca4`
- `0x180034e38`
- `0x180035158`
- `0x1800357e0`
- `0x180038fb4`

## pseudocode

```c
void __fastcall File::MapInWriteChunk(File *this, unsigned __int64 a2, __int64 a3)
{
  union _LARGE_INTEGER *v3; // rbx
  __int64 v5; // rsi
  unsigned int v8; // eax
  int v9; // r14d
  unsigned int v10; // eax
  unsigned int v11; // r14d
  int v12; // edx
  int v13; // r8d
  __int64 v14; // r8
  const wchar_t *v15; // rcx
  __int64 v16; // rax
  int v17; // eax
  unsigned __int64 v18; // [rsp+30h] [rbp-40h] BYREF
  struct _EVENT_DATA_DESCRIPTOR pExceptionObject; // [rsp+38h] [rbp-38h] BYREF
  const wchar_t *v20; // [rsp+48h] [rbp-28h]
  int v21; // [rsp+50h] [rbp-20h]
  int v22; // [rsp+54h] [rbp-1Ch]
  int v23; // [rsp+58h] [rbp-18h]
  char v24; // [rsp+5Ch] [rbp-14h]

  v3 = (union _LARGE_INTEGER *)((char *)this + 152);
  v5 = (a2 << 16) + 4096;
  if ( *((_QWORD *)this + 21) != v5 )
  {
    ValidateChunkNumber(a2, *((_QWORD *)this + 7));
    if ( *((_BYTE *)this + 826) )
    {
      v8 = File::WriteCurrentChunk((__int64)this, 1, a3);
      v9 = v8;
      if ( v8 )
      {
        if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, &WPP_b0e12c676fa238c8d52327699eb18844_Traceguids, v8);
        }
        *(_QWORD *)&pExceptionObject.Size = 0;
        pExceptionObject.Ptr = (ULONGLONG)&word_18004024A;
        v20 = 0;
        v23 = -1;
        v21 = v9;
        v22 = -1;
        v24 = 0;
        throw (EvtException *)&pExceptionObject;
      }
    }
    v10 = WriteFileView::TryAllocIfNecessary((WriteFileView *)v3);
    v11 = v10;
    if ( v10 )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, &WPP_b0e12c676fa238c8d52327699eb18844_Traceguids, v10);
      }
      *(_QWORD *)&pExceptionObject.Size = 0;
      pExceptionObject.Ptr = (ULONGLONG)&word_18004024A;
      v20 = 0;
      v23 = -1;
      v21 = v11;
      v22 = -1;
      v24 = 0;
      throw (EvtException *)&pExceptionObject;
    }
    FileView::ReadIn(v3 + 1, *((void **)this + 84), (union _LARGE_INTEGER)v5);
    if ( !VerifyChunk((const struct FileView *)&v3[1]) )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_iS(*((_QWORD *)WPP_GLOBAL_Control + 2), v12, v13, a2, *((_QWORD *)this + 85));
      }
      v18 = 0;
      if ( *((_BYTE *)this + 836) || !File::DetermineFirstRecordForRecovery(this, a2, &v18) )
      {
        *((_QWORD *)this + 21) = -1;
        *((_BYTE *)this + 830) = 0;
        if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, &WPP_b0e12c676fa238c8d52327699eb18844_Traceguids, 1500);
        }
        v20 = 0;
        v21 = 1500;
        v22 = -1;
        pExceptionObject = 0;
        v23 = 742;
        throw (EvtException *)&pExceptionObject;
      }
      InitializeChunkHeaderInfo(*((struct ChunkHeader **)this + 20), v18);
      memset_0(*((void **)this + 28), 0, 0x100u);
      memset_0(*((void **)this + 63), 0, 0x80u);
      *((_BYTE *)this + 827) = 1;
      *((_BYTE *)this + 836) = 1;
      if ( (Microsoft_Windows_EventlogEnableBits & 1) != 0 )
      {
        v15 = (const wchar_t *)*((_QWORD *)this + 89);
        if ( v15 )
        {
          v16 = -1;
          do
            ++v16;
          while ( v15[v16] );
          v17 = 2 * v16 + 2;
        }
        else
        {
          v15 = L"NULL";
          v17 = 10;
        }
        v21 = v17;
        v20 = v15;
        v22 = 0;
        McGenEventWrite_EventWriteTransfer((__int64)v15, &LOG_DROPPED_CHUNK, v14, 2u, &pExceptionObject);
      }
    }
  }
}

```

## disassembly

```asm
0x180032bb8  push    rbp
0x180032bba  push    rbx
0x180032bbb  push    rsi
0x180032bbc  push    rdi
0x180032bbd  push    r12
0x180032bbf  push    r14
0x180032bc1  push    r15
0x180032bc3  mov     rbp, rsp
0x180032bc6  sub     rsp, 70h
0x180032bca  mov     rax, cs:__security_cookie
0x180032bd1  xor     rax, rsp
0x180032bd4  mov     [rbp+var_10], rax
0x180032bd8  mov     rsi, rdx
0x180032bdb  lea     rbx, [rcx+98h]
0x180032be2  shl     rsi, 10h
0x180032be6  mov     r14, r8
0x180032be9  add     rsi, 1000h
0x180032bf0  mov     r15, rdx
0x180032bf3  mov     rdi, rcx
0x180032bf6  cmp     [rbx+10h], rsi
0x180032bfa  jz      loc_180032E54
0x180032c00  mov     rdx, [rcx+38h]
0x180032c04  mov     rcx, r15
0x180032c07  call    ValidateChunkNumber
0x180032c0c  xor     r12d, r12d
0x180032c0f  cmp     [rdi+33Ah], r12b
0x180032c16  jz      loc_180032CA5
0x180032c1c  mov     r8, r14
0x180032c1f  mov     dl, 1
0x180032c21  mov     rcx, rdi
0x180032c24  call    ?WriteCurrentChunk@File@@AEAAK_NAEAV?$unique_lock@Vshared_mutex@utl@@@utl@@@Z; File::WriteCurrentChunk(bool,utl::unique_lock<utl::shared_mutex> &)
0x180032c29  mov     r14d, eax
0x180032c2c  test    eax, eax
0x180032c2e  jz      short loc_180032CA5
0x180032c30  mov     rcx, cs:WPP_GLOBAL_Control
0x180032c37  lea     rsi, WPP_GLOBAL_Control
0x180032c3e  cmp     rcx, rsi
0x180032c41  jz      short loc_180032C6B
0x180032c43  mov     ebx, 8000h
0x180032c48  test    [rcx+1Ch], ebx
0x180032c4b  jz      short loc_180032C6B
0x180032c4d  cmp     byte ptr [rcx+19h], 2
0x180032c51  jb      short loc_180032C6B
0x180032c53  mov     rcx, [rcx+10h]
0x180032c57  lea     edx, [r12+24h]
0x180032c5c  mov     r9d, eax
0x180032c5f  lea     r8, WPP_b0e12c676fa238c8d52327699eb18844_Traceguids
0x180032c66  call    WPP_SF_D
0x180032c6b  lea     rax, word_18004024A
0x180032c72  mov     qword ptr [rbp+pExceptionObject+8], r12
0x180032c76  mov     qword ptr [rbp+pExceptionObject], rax
0x180032c7a  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180032c81  or      rax, 0FFFFFFFFFFFFFFFFh
0x180032c85  mov     [rbp+var_28], r12
0x180032c89  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180032c8d  mov     [rbp+var_18], eax
0x180032c90  mov     [rbp+var_20], r14d
0x180032c94  mov     [rbp+var_1C], 0FFFFFFFFh
0x180032c9b  mov     [rbp+var_14], r12b
0x180032c9f  call    _CxxThrowException_0
0x180032ca5  mov     rcx, rbx; this
0x180032ca8  call    ?TryAllocIfNecessary@WriteFileView@@QEAAKXZ; WriteFileView::TryAllocIfNecessary(void)
0x180032cad  mov     r14d, eax
0x180032cb0  test    eax, eax
0x180032cb2  jz      short loc_180032D29
0x180032cb4  mov     rcx, cs:WPP_GLOBAL_Control
0x180032cbb  lea     rsi, WPP_GLOBAL_Control
0x180032cc2  cmp     rcx, rsi
0x180032cc5  jz      short loc_180032CEF
0x180032cc7  mov     ebx, 8000h
0x180032ccc  test    [rcx+1Ch], ebx
0x180032ccf  jz      short loc_180032CEF
0x180032cd1  cmp     byte ptr [rcx+19h], 2
0x180032cd5  jb      short loc_180032CEF
0x180032cd7  mov     rcx, [rcx+10h]
0x180032cdb  lea     r8, WPP_b0e12c676fa238c8d52327699eb18844_Traceguids
0x180032ce2  mov     edx, 25h ; '%'
0x180032ce7  mov     r9d, eax
0x180032cea  call    WPP_SF_D
0x180032cef  lea     rax, word_18004024A
0x180032cf6  mov     qword ptr [rbp+pExceptionObject+8], r12
0x180032cfa  mov     qword ptr [rbp+pExceptionObject], rax
0x180032cfe  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180032d05  or      rax, 0FFFFFFFFFFFFFFFFh
0x180032d09  mov     [rbp+var_28], r12
0x180032d0d  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180032d11  mov     [rbp+var_18], eax
0x180032d14  mov     [rbp+var_20], r14d
0x180032d18  mov     [rbp+var_1C], 0FFFFFFFFh
0x180032d1f  mov     [rbp+var_14], r12b
0x180032d23  call    _CxxThrowException_0
0x180032d29  mov     rdx, [rdi+2A0h]; void *
0x180032d30  lea     rcx, [rbx+8]; this
0x180032d34  mov     r8, rsi; unsigned __int64
0x180032d37  call    ?ReadIn@FileView@@QEAAXPEAX_K@Z; FileView::ReadIn(void *,unsigned __int64)
0x180032d3c  lea     rcx, [rbx+8]; struct FileView *
0x180032d40  call    ?VerifyChunk@@YA_NAEBVFileView@@@Z; VerifyChunk(FileView const &)
0x180032d45  test    al, al
0x180032d47  jnz     loc_180032E54
0x180032d4d  mov     rcx, cs:WPP_GLOBAL_Control
0x180032d54  lea     rsi, WPP_GLOBAL_Control
0x180032d5b  mov     ebx, 8000h
0x180032d60  cmp     rcx, rsi
0x180032d63  jz      short loc_180032D88
0x180032d65  test    [rcx+1Ch], ebx
0x180032d68  jz      short loc_180032D88
0x180032d6a  cmp     byte ptr [rcx+19h], 4
0x180032d6e  jb      short loc_180032D88
0x180032d70  mov     rax, [rdi+2A8h]
0x180032d77  mov     r9, r15
0x180032d7a  mov     rcx, [rcx+10h]
0x180032d7e  mov     [rsp+70h+var_50], rax
0x180032d83  call    WPP_SF_iS
0x180032d88  mov     [rbp+var_40], r12
0x180032d8c  cmp     [rdi+344h], r12b
0x180032d93  jnz     loc_180032E6F
0x180032d99  lea     r8, [rbp+var_40]; unsigned __int64 *
0x180032d9d  mov     rdx, r15; unsigned __int64
0x180032da0  mov     rcx, rdi; this
0x180032da3  call    ?DetermineFirstRecordForRecovery@File@@AEAA_N_KAEA_K@Z; File::DetermineFirstRecordForRecovery(unsigned __int64,unsigned __int64 &)
0x180032da8  test    al, al
0x180032daa  jz      loc_180032E6F
0x180032db0  mov     rdx, [rbp+var_40]; unsigned __int64
0x180032db4  mov     rcx, [rdi+0A0h]; struct ChunkHeader *
0x180032dbb  call    ?InitializeChunkHeaderInfo@@YAXPEAUChunkHeader@@_K@Z; InitializeChunkHeaderInfo(ChunkHeader *,unsigned __int64)
0x180032dc0  mov     rcx, [rdi+0E0h]; void *
0x180032dc7  xor     edx, edx; Val
0x180032dc9  mov     r8d, 100h; Size
0x180032dcf  call    memset_0
0x180032dd4  mov     rcx, [rdi+1F8h]; void *
0x180032ddb  xor     edx, edx; Val
0x180032ddd  mov     r8d, 80h; Size
0x180032de3  call    memset_0
0x180032de8  mov     byte ptr [rdi+33Bh], 1
0x180032def  mov     byte ptr [rdi+344h], 1
0x180032df6  test    cs:Microsoft_Windows_EventlogEnableBits, 1
0x180032dfd  jz      short loc_180032E54
0x180032dff  mov     rcx, [rdi+2C8h]
0x180032e06  test    rcx, rcx
0x180032e09  jz      short loc_180032E22
0x180032e0b  or      rax, 0FFFFFFFFFFFFFFFFh
0x180032e0f  inc     rax
0x180032e12  cmp     [rcx+rax*2], r12w
0x180032e17  jnz     short loc_180032E0F
0x180032e19  lea     eax, ds:2[rax*2]
0x180032e20  jmp     short loc_180032E2E
0x180032e22  lea     rcx, aNull; "NULL"
0x180032e29  mov     eax, 0Ah
0x180032e2e  mov     [rbp+var_20], eax
0x180032e31  lea     rdx, LOG_DROPPED_CHUNK
0x180032e38  lea     rax, [rbp+pExceptionObject]
0x180032e3c  mov     [rbp+var_28], rcx
0x180032e40  mov     r9d, 2
0x180032e46  mov     [rsp+70h+var_50], rax
0x180032e4b  mov     [rbp+var_1C], r12d
0x180032e4f  call    McGenEventWrite_EventWriteTransfer
0x180032e54  mov     rcx, [rbp+var_10]
0x180032e58  xor     rcx, rsp; StackCookie
0x180032e5b  call    __security_check_cookie
0x180032e60  add     rsp, 70h
0x180032e64  pop     r15
0x180032e66  pop     r14
0x180032e68  pop     r12
0x180032e6a  pop     rdi
0x180032e6b  pop     rsi
0x180032e6c  pop     rbx
0x180032e6d  pop     rbp
0x180032e6e  retn
0x180032e6f  or      rax, 0FFFFFFFFFFFFFFFFh
0x180032e73  mov     [rdi+0A8h], rax
0x180032e7a  mov     [rdi+33Eh], r12b
0x180032e81  mov     rcx, cs:WPP_GLOBAL_Control
0x180032e88  mov     edi, 5DCh
0x180032e8d  cmp     rcx, rsi
0x180032e90  jz      short loc_180032EB3
0x180032e92  test    [rcx+1Ch], ebx
0x180032e95  jz      short loc_180032EB3
0x180032e97  cmp     byte ptr [rcx+19h], 2
0x180032e9b  jb      short loc_180032EB3
0x180032e9d  mov     rcx, [rcx+10h]
0x180032ea1  lea     edx, [rax+28h]
0x180032ea4  mov     r9d, edi
0x180032ea7  lea     r8, WPP_b0e12c676fa238c8d52327699eb18844_Traceguids
0x180032eae  call    WPP_SF_D
0x180032eb3  xorps   xmm0, xmm0
0x180032eb6  mov     [rbp+var_28], r12
0x180032eba  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180032ec1  mov     [rbp+var_20], edi
0x180032ec4  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180032ec8  mov     [rbp+var_1C], 0FFFFFFFFh
0x180032ecf  movdqu  [rbp+pExceptionObject], xmm0
0x180032ed4  mov     [rbp+var_18], 2E6h
0x180032edb  call    _CxxThrowException_0
```
