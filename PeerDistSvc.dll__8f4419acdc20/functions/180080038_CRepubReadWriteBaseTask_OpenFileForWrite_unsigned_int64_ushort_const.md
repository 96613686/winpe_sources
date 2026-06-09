# CRepubReadWriteBaseTask::OpenFileForWrite(unsigned __int64,ushort const *)

- ea: `0x180080038`
- end: `0x1800801df`
- name: `?OpenFileForWrite@CRepubReadWriteBaseTask@@IEAAK_KPEBG@Z`
- size: `423`
- prototype: `__int64 __fastcall(CRepubReadWriteBaseTask *this, unsigned __int64, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, service_task`

## callers

- `0x18007c658`

## callees

- `0x1800024a4`
- `0x18000cf48`
- `0x18000ecf4`
- `0x180048854`
- `0x180080038`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180080093`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180080102`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180080093`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180080102`
- `KERNEL32!CloseHandle` at `0x18008014d`
- `KERNEL32!CloseHandle` at `0x18008014d`
- `KERNEL32!CreateFileW` at `0x180080084`
- `KERNEL32!CreateFileW` at `0x180080084`
- `api-ms-win-core-file-l2-1-0!ReOpenFile` at `0x1800800f3`
- `api-ms-win-core-file-l2-1-0!ReOpenFile` at `0x1800800f3`

## pseudocode

```c
__int64 __fastcall CRepubReadWriteBaseTask::OpenFileForWrite(
        CRepubReadWriteBaseTask *this,
        unsigned __int64 a2,
        const unsigned __int16 *a3)
{
  int v3; // ebx
  HANDLE FileW; // rax
  void *v7; // rsi
  DWORD LastError; // edi
  HANDLE v9; // r12
  volatile signed __int32 *v10; // rax
  struct CRepubFileHandle *v11; // rbx

  v3 = (int)a3;
  FileW = CreateFileW(a3, 0x40000000u, 3u, 0, 4u, 0x60000000u, 0);
  v7 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 12),
        51,
        (unsigned int)WPP_3b231073c17c3a7554274eb2955bc7c1_Traceguids,
        v3,
        LastError);
    }
  }
  else
  {
    v9 = ReOpenFile(FileW, 0x80000000, 3u, 0x40000000u);
    if ( v9 == (HANDLE)-1LL )
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 12),
          52,
          (unsigned int)WPP_3b231073c17c3a7554274eb2955bc7c1_Traceguids,
          v3,
          LastError);
      }
      if ( v7 )
        CloseHandle(v7);
    }
    else
    {
      LastError = 0;
      v10 = (volatile signed __int32 *)operator new(0x40u);
      v11 = (struct CRepubFileHandle *)v10;
      if ( v10 )
      {
        *((_DWORD *)v10 + 2) = 0;
        *(_QWORD *)v10 = &CRepubFileHandle::`vftable';
        *((_DWORD *)v10 + 4) = 0;
        *((_QWORD *)v10 + 3) = a2;
        *((_QWORD *)v10 + 4) = &ObjectHandle::`vftable';
        *((_QWORD *)v10 + 5) = v7;
        *((_QWORD *)v10 + 6) = &ObjectHandle::`vftable';
        *((_QWORD *)v10 + 7) = v9;
        _InterlockedIncrement(v10 + 2);
      }
      else
      {
        v11 = 0;
      }
      SmartPointer<CRepubJetSessionContext>::Release((char *)this + 648);
      *((_QWORD *)this + 81) = v11;
      CRepubFileStore::InsertFileHandle(*((CRepubFileStore **)this + 76), a2, v11);
    }
  }
  return LastError;
}

```

## disassembly

```asm
0x180080038  mov     rax, rsp
0x18008003b  mov     [rax+8], rbx
0x18008003f  mov     [rax+10h], rbp
0x180080043  push    rsi
0x180080044  push    rdi
0x180080045  push    r12
0x180080047  push    r14
0x180080049  push    r15
0x18008004b  sub     rsp, 40h
0x18008004f  mov     rbx, r8
0x180080052  mov     r15, rdx
0x180080055  mov     rbp, rcx
0x180080058  mov     qword ptr [rax-38h], 0
0x180080060  mov     dword ptr [rax-40h], 60000000h
0x180080067  mov     dword ptr [rax-48h], 4
0x18008006e  xor     r9d, r9d; lpSecurityAttributes
0x180080071  lea     edi, [r9+3]
0x180080075  mov     r8d, edi; dwShareMode
0x180080078  mov     r14d, 40000000h
0x18008007e  mov     edx, r14d; dwDesiredAccess
0x180080081  mov     rcx, rbx; lpFileName
0x180080084  call    cs:__imp_CreateFileW
0x18008008a  mov     rsi, rax
0x18008008d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180080091  jnz     short loc_1800800E5
0x180080093  call    cs:__imp_GetLastError
0x180080099  mov     edi, eax
0x18008009b  lea     rax, WPP_GLOBAL_Control
0x1800800a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800800a9  cmp     rcx, rax
0x1800800ac  jz      loc_1800801C6
0x1800800b2  test    byte ptr [rcx+6Ch], 4
0x1800800b6  jz      loc_1800801C6
0x1800800bc  cmp     byte ptr [rcx+69h], 1
0x1800800c0  jb      loc_1800801C6
0x1800800c6  lea     edx, [rsi+34h]
0x1800800c9  mov     [rsp+68h+var_48], edi
0x1800800cd  mov     r9, rbx
0x1800800d0  lea     r8, WPP_3b231073c17c3a7554274eb2955bc7c1_Traceguids
0x1800800d7  mov     rcx, [rcx+60h]
0x1800800db  call    WPP_SF_Sd
0x1800800e0  jmp     loc_1800801C6
0x1800800e5  mov     r9d, r14d; dwFlagsAndAttributes
0x1800800e8  mov     r8d, edi; dwShareMode
0x1800800eb  mov     edx, 80000000h; dwDesiredAccess
0x1800800f0  mov     rcx, rsi; hOriginalFile
0x1800800f3  call    cs:__imp_ReOpenFile
0x1800800f9  mov     r12, rax
0x1800800fc  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180080100  jnz     short loc_180080155
0x180080102  call    cs:__imp_GetLastError
0x180080108  mov     edi, eax
0x18008010a  lea     rax, WPP_GLOBAL_Control
0x180080111  mov     rcx, cs:WPP_GLOBAL_Control
0x180080118  cmp     rcx, rax
0x18008011b  jz      short loc_180080145
0x18008011d  test    byte ptr [rcx+6Ch], 4
0x180080121  jz      short loc_180080145
0x180080123  cmp     byte ptr [rcx+69h], 1
0x180080127  jb      short loc_180080145
0x180080129  lea     edx, [r12+35h]
0x18008012e  mov     [rsp+68h+var_48], edi
0x180080132  mov     r9, rbx
0x180080135  lea     r8, WPP_3b231073c17c3a7554274eb2955bc7c1_Traceguids
0x18008013c  mov     rcx, [rcx+60h]
0x180080140  call    WPP_SF_Sd
0x180080145  test    rsi, rsi
0x180080148  jz      short loc_1800801C6
0x18008014a  mov     rcx, rsi; hObject
0x18008014d  call    cs:__imp_CloseHandle
0x180080153  jmp     short loc_1800801C6
0x180080155  xor     edi, edi
0x180080157  lea     r14, [rbp+288h]
0x18008015e  lea     ecx, [rdi+40h]; Size
0x180080161  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180080166  mov     rbx, rax
0x180080169  mov     [rsp+68h+arg_18], rax
0x180080171  test    rax, rax
0x180080174  jz      short loc_1800801A7
0x180080176  mov     [rax+8], edi
0x180080179  lea     rax, ??_7CRepubFileHandle@@6B@; const CRepubFileHandle::`vftable'
0x180080180  mov     [rbx], rax
0x180080183  mov     [rbx+10h], edi
0x180080186  mov     [rbx+18h], r15
0x18008018a  lea     rax, ??_7ObjectHandle@@6B@; const ObjectHandle::`vftable'
0x180080191  mov     [rbx+20h], rax
0x180080195  mov     [rbx+28h], rsi
0x180080199  mov     [rbx+30h], rax
0x18008019d  mov     [rbx+38h], r12
0x1800801a1  lock inc dword ptr [rbx+8]
0x1800801a5  jmp     short loc_1800801A9
0x1800801a7  xor     ebx, ebx
0x1800801a9  mov     rcx, r14
0x1800801ac  call    ?Release@?$SmartPointer@VCRepubJetSessionContext@@@@IEAAXXZ; SmartPointer<CRepubJetSessionContext>::Release(void)
0x1800801b1  mov     [r14], rbx
0x1800801b4  mov     r8, rbx; struct CRepubFileHandle *
0x1800801b7  mov     rdx, r15; unsigned __int64
0x1800801ba  mov     rcx, [rbp+260h]; this
0x1800801c1  call    ?InsertFileHandle@CRepubFileStore@@QEAAX_KPEAVCRepubFileHandle@@@Z; CRepubFileStore::InsertFileHandle(unsigned __int64,CRepubFileHandle *)
0x1800801c6  mov     eax, edi
0x1800801c8  mov     rbx, [rsp+68h+arg_0]
0x1800801cd  mov     rbp, [rsp+68h+arg_8]
0x1800801d2  add     rsp, 40h
0x1800801d6  pop     r15
0x1800801d8  pop     r14
0x1800801da  pop     r12
0x1800801dc  pop     rdi
0x1800801dd  pop     rsi
0x1800801de  retn
```
