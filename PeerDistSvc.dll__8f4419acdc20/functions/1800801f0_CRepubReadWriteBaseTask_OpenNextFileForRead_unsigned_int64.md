# CRepubReadWriteBaseTask::OpenNextFileForRead(unsigned __int64)

- ea: `0x1800801f0`
- end: `0x180080565`
- name: `?OpenNextFileForRead@CRepubReadWriteBaseTask@@MEAAK_K@Z`
- size: `885`
- prototype: `__int64 __fastcall(CRepubFileStore **this, unsigned __int64)`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, service_task`

## callees

- `0x1800024a4`
- `0x1800024f0`
- `0x180008290`
- `0x1800082d0`
- `0x180008310`
- `0x18000cf48`
- `0x18000ecf4`
- `0x180044d50`
- `0x180048854`
- `0x18006116c`
- `0x1800801f0`
- `0x180159010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008040a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180080478`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008040a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180080478`
- `KERNEL32!CloseHandle` at `0x1800804c7`
- `KERNEL32!CloseHandle` at `0x1800804c7`
- `KERNEL32!CreateFileW` at `0x1800803fb`
- `KERNEL32!CreateFileW` at `0x1800803fb`
- `api-ms-win-core-file-l2-1-0!ReOpenFile` at `0x180080469`
- `api-ms-win-core-file-l2-1-0!ReOpenFile` at `0x180080469`

## pseudocode

```c
__int64 __fastcall CRepubReadWriteBaseTask::OpenNextFileForRead(CRepubFileStore **this, unsigned __int64 a2)
{
  WCHAR *v4; // rbx
  unsigned int FileHandle; // eax
  DWORD v6; // esi
  CHostedCacheMsgEncoding *v7; // rcx
  __int64 v8; // rdx
  DWORD v9; // eax
  HANDLE FileW; // rax
  void *v11; // rdi
  DWORD LastError; // eax
  HANDLE v13; // r12
  volatile signed __int32 *v14; // rax
  struct CRepubFileHandle *v15; // r14
  LPCWSTR lpFileName; // [rsp+80h] [rbp+8h] BYREF
  LPCWSTR v18; // [rsp+90h] [rbp+18h]
  unsigned __int64 v19; // [rsp+98h] [rbp+20h] BYREF

  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 12), 59, WPP_3b231073c17c3a7554274eb2955bc7c1_Traceguids);
  }
  v4 = 0;
  v18 = 0;
  lpFileName = 0;
  FileHandle = CRepubFileStore::GetFileHandle(this[76], a2, (struct CRepubFileHandle **)&lpFileName);
  v6 = FileHandle;
  if ( !FileHandle )
  {
    SmartPointer<CRepubJetSessionContext>::Release(this + 81);
    this[81] = (CRepubFileStore *)lpFileName;
    goto LABEL_39;
  }
  if ( FileHandle == 1168 )
  {
    FileHandle = (*((__int64 (__fastcall **)(CRepubFileStore **))*this + 17))(this);
    v6 = FileHandle;
    if ( FileHandle )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        v8 = 61;
        goto LABEL_12;
      }
    }
    else
    {
      lpFileName = 0;
      v9 = ConstructRepubFilePath(
             a2,
             *((_DWORD *)this[76] + 56),
             *((_DWORD *)this[76] + 57),
             (const unsigned __int16 *)this[75] + 10,
             0,
             *((_QWORD *)this[75] + 78),
             (unsigned __int16 **)&lpFileName,
             &v19);
      v6 = v9;
      if ( v9 )
      {
        if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 105) )
        {
          WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 12), 62, WPP_3b231073c17c3a7554274eb2955bc7c1_Traceguids, a2, v9);
        }
      }
      else
      {
        operator delete(0);
        v4 = (WCHAR *)lpFileName;
        v18 = lpFileName;
        FileW = CreateFileW(lpFileName, 0x80000000, 3u, 0, 3u, 0x40000000u, 0);
        v11 = FileW;
        if ( FileW == (HANDLE)-1LL )
        {
          LastError = GetLastError();
          v6 = LastError;
          if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 105) )
          {
            WPP_SF_Sd(
              *((_QWORD *)WPP_GLOBAL_Control + 12),
              63,
              (unsigned int)WPP_3b231073c17c3a7554274eb2955bc7c1_Traceguids,
              (_DWORD)v4,
              LastError);
          }
        }
        else
        {
          v13 = ReOpenFile(FileW, 0x40000000u, 3u, 0x60000000u);
          if ( v13 == (HANDLE)-1LL )
          {
            v6 = GetLastError();
            if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 105) )
            {
              WPP_SF_Sd(
                *((_QWORD *)WPP_GLOBAL_Control + 12),
                64,
                (unsigned int)WPP_3b231073c17c3a7554274eb2955bc7c1_Traceguids,
                (_DWORD)v4,
                v6);
            }
            if ( v11 )
              CloseHandle(v11);
          }
          else
          {
            v14 = (volatile signed __int32 *)operator new(0x40u);
            v15 = (struct CRepubFileHandle *)v14;
            lpFileName = (LPCWSTR)v14;
            if ( v14 )
            {
              *((_DWORD *)v14 + 2) = 0;
              *(_QWORD *)v14 = &CRepubFileHandle::`vftable';
              *((_DWORD *)v14 + 4) = 0;
              *((_QWORD *)v14 + 3) = a2;
              *((_QWORD *)v14 + 4) = &ObjectHandle::`vftable';
              *((_QWORD *)v14 + 5) = v13;
              *((_QWORD *)v14 + 6) = &ObjectHandle::`vftable';
              *((_QWORD *)v14 + 7) = v11;
              _InterlockedIncrement(v14 + 2);
            }
            else
            {
              v15 = 0;
            }
            SmartPointer<CRepubJetSessionContext>::Release(this + 81);
            this[81] = v15;
            CRepubFileStore::InsertFileHandle(this[76], a2, v15);
          }
        }
      }
    }
  }
  else
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      v8 = 60;
LABEL_12:
      WPP_SF_d(*((_QWORD *)v7 + 12), v8, WPP_3b231073c17c3a7554274eb2955bc7c1_Traceguids, FileHandle);
    }
  }
LABEL_39:
  operator delete(v4);
  return v6;
}

```

## disassembly

```asm
0x1800801f0  push    rbx
0x1800801f2  push    rbp
0x1800801f3  push    rsi
0x1800801f4  push    rdi
0x1800801f5  push    r12
0x1800801f7  push    r14
0x1800801f9  push    r15
0x1800801fb  sub     rsp, 40h
0x1800801ff  mov     rbp, rdx
0x180080202  mov     r15, rcx
0x180080205  lea     r12, WPP_GLOBAL_Control
0x18008020c  lea     rdi, WPP_3b231073c17c3a7554274eb2955bc7c1_Traceguids
0x180080213  mov     r14b, 4
0x180080216  mov     rcx, cs:WPP_GLOBAL_Control
0x18008021d  cmp     rcx, r12
0x180080220  jz      short loc_180080242
0x180080222  test    [rcx+6Ch], r14b
0x180080226  jz      short loc_180080242
0x180080228  cmp     [rcx+69h], r14b
0x18008022c  jb      short loc_180080242
0x18008022e  mov     edx, 3Bh ; ';'
0x180080233  mov     r9, rbp
0x180080236  mov     r8, rdi
0x180080239  mov     rcx, [rcx+60h]
0x18008023d  call    WPP_SF_q
0x180080242  xor     ebx, ebx
0x180080244  mov     [rsp+78h+arg_10], rbx
0x18008024c  mov     [rsp+78h+lpFileName], rbx
0x180080254  lea     r8, [rsp+78h+lpFileName]; struct CRepubFileHandle **
0x18008025c  mov     rdx, rbp; unsigned __int64
0x18008025f  mov     rcx, [r15+260h]; this
0x180080266  call    ?GetFileHandle@CRepubFileStore@@QEAAK_KPEAPEAVCRepubFileHandle@@@Z; CRepubFileStore::GetFileHandle(unsigned __int64,CRepubFileHandle * *)
0x18008026b  mov     esi, eax
0x18008026d  test    eax, eax
0x18008026f  jnz     short loc_180080290
0x180080271  lea     rdi, [r15+288h]
0x180080278  mov     rcx, rdi
0x18008027b  call    ?Release@?$SmartPointer@VCRepubJetSessionContext@@@@IEAAXXZ; SmartPointer<CRepubJetSessionContext>::Release(void)
0x180080280  mov     rcx, [rsp+78h+lpFileName]
0x180080288  mov     [rdi], rcx
0x18008028b  jmp     loc_18008054C
0x180080290  cmp     eax, 490h
0x180080295  jz      short loc_1800802D4
0x180080297  mov     rcx, cs:WPP_GLOBAL_Control
0x18008029e  cmp     rcx, r12
0x1800802a1  jz      loc_18008054C
0x1800802a7  test    [rcx+6Ch], r14b
0x1800802ab  jz      loc_18008054C
0x1800802b1  cmp     byte ptr [rcx+69h], 1
0x1800802b5  jb      loc_18008054C
0x1800802bb  mov     edx, 3Ch ; '<'
0x1800802c0  mov     r9d, eax
0x1800802c3  mov     r8, rdi
0x1800802c6  mov     rcx, [rcx+60h]
0x1800802ca  call    WPP_SF_d
0x1800802cf  jmp     loc_18008054C
0x1800802d4  mov     rax, [r15]
0x1800802d7  mov     rcx, r15
0x1800802da  mov     rax, [rax+88h]
0x1800802e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800802e6  mov     esi, eax
0x1800802e8  test    eax, eax
0x1800802ea  jz      short loc_180080317
0x1800802ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1800802f3  cmp     rcx, r12
0x1800802f6  jz      loc_18008054C
0x1800802fc  test    [rcx+6Ch], r14b
0x180080300  jz      loc_18008054C
0x180080306  cmp     byte ptr [rcx+69h], 1
0x18008030a  jb      loc_18008054C
0x180080310  mov     edx, 3Dh ; '='
0x180080315  jmp     short loc_1800802C0
0x180080317  mov     [rsp+78h+lpFileName], 0
0x180080323  mov     rax, [r15+258h]
0x18008032a  mov     rdx, [r15+260h]
0x180080331  lea     r9, [rax+14h]; unsigned __int16 *
0x180080335  lea     rcx, [rsp+78h+arg_18]
0x18008033d  mov     [rsp+78h+var_40], rcx; unsigned __int64 *
0x180080342  lea     rcx, [rsp+78h+lpFileName]
0x18008034a  mov     [rsp+78h+hTemplateFile], rcx; unsigned __int16 **
0x18008034f  mov     rax, [rax+270h]
0x180080356  mov     qword ptr [rsp+78h+dwFlagsAndAttributes], rax; unsigned __int64
0x18008035b  mov     byte ptr [rsp+78h+dwCreationDisposition], 0; bool
0x180080360  mov     r8d, [rdx+0E4h]; unsigned int
0x180080367  mov     edx, [rdx+0E0h]; unsigned int
0x18008036d  mov     rcx, rbp; unsigned __int64
0x180080370  call    ?ConstructRepubFilePath@@YAK_KKKPEBG_N0PEAPEAGPEA_K@Z; ConstructRepubFilePath(unsigned __int64,ulong,ulong,ushort const *,bool,unsigned __int64,ushort * *,unsigned __int64 *)
0x180080375  mov     esi, eax
0x180080377  test    eax, eax
0x180080379  jz      short loc_1800803BC
0x18008037b  mov     rcx, cs:WPP_GLOBAL_Control
0x180080382  cmp     rcx, r12
0x180080385  jz      loc_18008054C
0x18008038b  test    [rcx+6Ch], r14b
0x18008038f  jz      loc_18008054C
0x180080395  cmp     byte ptr [rcx+69h], 1
0x180080399  jb      loc_18008054C
0x18008039f  mov     edx, 3Eh ; '>'
0x1800803a4  mov     [rsp+78h+dwCreationDisposition], eax
0x1800803a8  mov     r9, rbp
0x1800803ab  mov     r8, rdi
0x1800803ae  mov     rcx, [rcx+60h]
0x1800803b2  call    WPP_SF_qD
0x1800803b7  jmp     loc_18008054C
0x1800803bc  xor     ecx, ecx; Block
0x1800803be  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800803c3  mov     rbx, [rsp+78h+lpFileName]
0x1800803cb  mov     [rsp+78h+arg_10], rbx
0x1800803d3  mov     [rsp+78h+hTemplateFile], 0; hTemplateFile
0x1800803dc  mov     [rsp+78h+dwFlagsAndAttributes], 40000000h; dwFlagsAndAttributes
0x1800803e4  mov     eax, 3
0x1800803e9  mov     [rsp+78h+dwCreationDisposition], eax; dwCreationDisposition
0x1800803ed  xor     r9d, r9d; lpSecurityAttributes
0x1800803f0  mov     r8d, eax; dwShareMode
0x1800803f3  mov     edx, 80000000h; dwDesiredAccess
0x1800803f8  mov     rcx, rbx; lpFileName
0x1800803fb  call    cs:__imp_CreateFileW
0x180080401  mov     rdi, rax
0x180080404  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180080408  jnz     short loc_180080455
0x18008040a  call    cs:__imp_GetLastError
0x180080410  mov     esi, eax
0x180080412  mov     rcx, cs:WPP_GLOBAL_Control
0x180080419  cmp     rcx, r12
0x18008041c  jz      loc_18008054C
0x180080422  test    [rcx+6Ch], r14b
0x180080426  jz      loc_18008054C
0x18008042c  cmp     byte ptr [rcx+69h], 1
0x180080430  jb      loc_18008054C
0x180080436  lea     edx, [rdi+40h]
0x180080439  mov     [rsp+78h+dwCreationDisposition], eax
0x18008043d  mov     r9, rbx
0x180080440  lea     r8, WPP_3b231073c17c3a7554274eb2955bc7c1_Traceguids
0x180080447  mov     rcx, [rcx+60h]
0x18008044b  call    WPP_SF_Sd
0x180080450  jmp     loc_18008054C
0x180080455  mov     edx, 40000000h; dwDesiredAccess
0x18008045a  mov     r9d, 60000000h; dwFlagsAndAttributes
0x180080460  mov     r8d, 3; dwShareMode
0x180080466  mov     rcx, rdi; hOriginalFile
0x180080469  call    cs:__imp_ReOpenFile
0x18008046f  mov     r12, rax
0x180080472  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180080476  jnz     short loc_1800804CF
0x180080478  call    cs:__imp_GetLastError
0x18008047e  mov     esi, eax
0x180080480  mov     rcx, cs:WPP_GLOBAL_Control
0x180080487  lea     rax, WPP_GLOBAL_Control
0x18008048e  cmp     rcx, rax
0x180080491  jz      short loc_1800804BB
0x180080493  test    [rcx+6Ch], r14b
0x180080497  jz      short loc_1800804BB
0x180080499  cmp     byte ptr [rcx+69h], 1
0x18008049d  jb      short loc_1800804BB
0x18008049f  lea     edx, [r12+41h]
0x1800804a4  mov     [rsp+78h+dwCreationDisposition], esi
0x1800804a8  mov     r9, rbx
0x1800804ab  lea     r8, WPP_3b231073c17c3a7554274eb2955bc7c1_Traceguids
0x1800804b2  mov     rcx, [rcx+60h]
0x1800804b6  call    WPP_SF_Sd
0x1800804bb  test    rdi, rdi
0x1800804be  jz      loc_18008054C
0x1800804c4  mov     rcx, rdi; hObject
0x1800804c7  call    cs:__imp_CloseHandle
0x1800804cd  jmp     short loc_18008054C
0x1800804cf  mov     ecx, 40h ; '@'; Size
0x1800804d4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800804d9  mov     r14, rax
0x1800804dc  mov     [rsp+78h+lpFileName], rax
0x1800804e4  test    rax, rax
0x1800804e7  jz      short loc_180080524
0x1800804e9  mov     dword ptr [rax+8], 0
0x1800804f0  lea     rax, ??_7CRepubFileHandle@@6B@; const CRepubFileHandle::`vftable'
0x1800804f7  mov     [r14], rax
0x1800804fa  mov     dword ptr [r14+10h], 0
0x180080502  mov     [r14+18h], rbp
0x180080506  lea     rax, ??_7ObjectHandle@@6B@; const ObjectHandle::`vftable'
0x18008050d  mov     [r14+20h], rax
0x180080511  mov     [r14+28h], r12
0x180080515  mov     [r14+30h], rax
0x180080519  mov     [r14+38h], rdi
0x18008051d  lock inc dword ptr [r14+8]
0x180080522  jmp     short loc_180080527
0x180080524  xor     r14d, r14d
0x180080527  lea     rdi, [r15+288h]
0x18008052e  mov     rcx, rdi
0x180080531  call    ?Release@?$SmartPointer@VCRepubJetSessionContext@@@@IEAAXXZ; SmartPointer<CRepubJetSessionContext>::Release(void)
0x180080536  mov     [rdi], r14
0x180080539  mov     r8, r14; struct CRepubFileHandle *
0x18008053c  mov     rdx, rbp; unsigned __int64
0x18008053f  mov     rcx, [r15+260h]; this
0x180080546  call    ?InsertFileHandle@CRepubFileStore@@QEAAX_KPEAVCRepubFileHandle@@@Z; CRepubFileStore::InsertFileHandle(unsigned __int64,CRepubFileHandle *)
0x18008054b  nop
0x18008054c  mov     rcx, rbx; Block
0x18008054f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180080554  mov     eax, esi
0x180080556  add     rsp, 40h
0x18008055a  pop     r15
0x18008055c  pop     r14
0x18008055e  pop     r12
0x180080560  pop     rdi
0x180080561  pop     rsi
0x180080562  pop     rbp
0x180080563  pop     rbx
0x180080564  retn
```
