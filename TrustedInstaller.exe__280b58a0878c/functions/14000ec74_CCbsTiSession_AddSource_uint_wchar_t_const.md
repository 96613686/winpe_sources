# CCbsTiSession::AddSource(uint,wchar_t const *)

- ea: `0x14000ec74`
- end: `0x14000edc8`
- name: `?AddSource@CCbsTiSession@@UEAAJIPEB_W@Z`
- size: `340`
- prototype: `__int64 __fastcall(CCbsTiSession *__hidden this, unsigned int, const wchar_t *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x14000ec60`

## callees

- `0x140006778`
- `0x14000e2ac`
- `0x14000e774`
- `0x14000ec74`
- `0x14001056c`
- `0x1400106c4`
- `0x140017658`
- `0x14001d404`
- `0x14002b010`

## string_xrefs

- `0x14000ecb2`: `Invalid argument: szBasePath.`

## pseudocode

```c
__int64 __fastcall CCbsTiSession::AddSource(CCbsTiSession *this, unsigned int a2, const wchar_t *a3)
{
  CCbsTiSession *v3; // rsi
  unsigned int v7; // ebx
  const char *v8; // r9
  __int64 v9; // rdx
  int SureWorkerSessionAvailable; // eax
  int v11; // eax
  __int64 v12; // rdi
  int RoomAt; // eax
  __int128 v14; // xmm0
  __int64 v15; // rax
  __int128 v17; // [rsp+20h] [rbp-68h] BYREF
  _BYTE v18[88]; // [rsp+30h] [rbp-58h] BYREF

  v3 = (CCbsTiSession *)((char *)this - 256);
  CritSecLocker::CritSecLocker((CritSecLocker *)v18, (CCbsTiSession *)((char *)this - 208), 1);
  if ( a3 )
  {
    if ( !*((_DWORD *)this - 34) )
    {
      *((_QWORD *)&v17 + 1) = 0;
      LODWORD(v17) = a2;
      v11 = SczAllocFromSz((char *)&v17 + 8, a3);
      v7 = v11;
      if ( v11 >= 0 )
      {
        v12 = *((_QWORD *)v3 + 26);
        RoomAt = CCbsArrayBase<CCbsTiSession::LocalSource,CCbsArray<CCbsTiSession::LocalSource>>::MakeRoomAt(
                   (char *)v3 + 184,
                   v12);
        v7 = RoomAt;
        if ( RoomAt >= 0 )
        {
          v14 = v17;
          v15 = *((_QWORD *)v3 + 28);
          *((_QWORD *)&v17 + 1) = 0;
          *(_OWORD *)(v15 + 16 * v12) = v14;
          CCbsTiSession::LocalSource::~LocalSource((CCbsTiSession::LocalSource *)&v17);
          v7 = 0;
          goto LABEL_16;
        }
        CBSWdsLogLight(0x4000000, (unsigned int)RoomAt, 1, "Failed to allocate resource", (_QWORD)v17);
      }
      else
      {
        CBSWdsLogLight(0x4000000, (unsigned int)v11, 1, "Failed to allocate string", (_QWORD)v17);
      }
      CCbsTiSession::LocalSource::~LocalSource((CCbsTiSession::LocalSource *)&v17);
      goto LABEL_16;
    }
    SureWorkerSessionAvailable = CCbsTiSession::MakeSureWorkerSessionAvailable(v3, 1);
    v7 = SureWorkerSessionAvailable;
    if ( SureWorkerSessionAvailable >= 0 )
    {
      SureWorkerSessionAvailable = (*(__int64 (__fastcall **)(_QWORD, _QWORD, const wchar_t *))(**((_QWORD **)this - 27)
                                                                                              + 120LL))(
                                     *((_QWORD *)this - 27),
                                     a2,
                                     a3);
      v7 = SureWorkerSessionAvailable;
      if ( SureWorkerSessionAvailable >= 0 )
        goto LABEL_16;
      v8 = "Failed to Add Source using worker session";
    }
    else
    {
      v8 = "Failed to get worker session.";
    }
    v9 = (unsigned int)SureWorkerSessionAvailable;
  }
  else
  {
    v7 = -2147467261;
    v8 = "Invalid argument: szBasePath.";
    v9 = 2147500035LL;
  }
  CBSWdsLogLight(0x4000000, v9, 1, v8);
LABEL_16:
  CritSecLocker::~CritSecLocker((CritSecLocker *)v18);
  return v7;
}

```

## disassembly

```asm
0x14000ec74  push    rbx
0x14000ec76  push    rbp
0x14000ec77  push    rsi
0x14000ec78  push    rdi
0x14000ec79  push    r12
0x14000ec7b  push    r14
0x14000ec7d  sub     rsp, 58h
0x14000ec81  lea     rsi, [rcx-100h]
0x14000ec88  mov     rbp, r8
0x14000ec8b  mov     r14d, edx
0x14000ec8e  mov     rdi, rcx
0x14000ec91  mov     r12d, 1
0x14000ec97  lea     rdx, [rsi+30h]; struct AutoCritSec *
0x14000ec9b  mov     r8b, r12b; bool
0x14000ec9e  lea     rcx, [rsp+88h+var_58]; this
0x14000eca3  call    ??0CritSecLocker@@QEAA@AEAVAutoCritSec@@_N@Z; CritSecLocker::CritSecLocker(AutoCritSec &,bool)
0x14000eca8  test    rbp, rbp
0x14000ecab  jnz     short loc_14000ECCD
0x14000ecad  mov     ebx, 80004003h
0x14000ecb2  lea     r9, aInvalidArgumen_31; "Invalid argument: szBasePath."
0x14000ecb9  mov     edx, ebx
0x14000ecbb  mov     r8d, r12d
0x14000ecbe  mov     ecx, 4000000h
0x14000ecc3  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14000ecc8  jmp     loc_14000EDAF
0x14000eccd  cmp     dword ptr [rdi-88h], 0
0x14000ecd4  jz      short loc_14000ED1E
0x14000ecd6  mov     dl, r12b; bool
0x14000ecd9  mov     rcx, rsi; this
0x14000ecdc  call    ?MakeSureWorkerSessionAvailable@CCbsTiSession@@QEAAJ_N@Z; CCbsTiSession::MakeSureWorkerSessionAvailable(bool)
0x14000ece1  mov     ebx, eax
0x14000ece3  test    eax, eax
0x14000ece5  jns     short loc_14000ECF2
0x14000ece7  lea     r9, aFailedToGetWor_1; "Failed to get worker session."
0x14000ecee  mov     edx, eax
0x14000ecf0  jmp     short loc_14000ECBB
0x14000ecf2  mov     rcx, [rdi-0D8h]
0x14000ecf9  mov     r8, rbp
0x14000ecfc  mov     edx, r14d
0x14000ecff  mov     rax, [rcx]
0x14000ed02  mov     rax, [rax+78h]
0x14000ed06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ed0b  mov     ebx, eax
0x14000ed0d  test    eax, eax
0x14000ed0f  jns     loc_14000EDAF
0x14000ed15  lea     r9, aFailedToAddSou; "Failed to Add Source using worker sessi"...
0x14000ed1c  jmp     short loc_14000ECEE
0x14000ed1e  mov     rdx, rbp
0x14000ed21  mov     qword ptr [rsp+88h+var_68+8], 0
0x14000ed2a  lea     rcx, [rsp+88h+var_68+8]
0x14000ed2f  mov     dword ptr [rsp+88h+var_68], r14d
0x14000ed34  call    SczAllocFromSz
0x14000ed39  mov     ebx, eax
0x14000ed3b  test    eax, eax
0x14000ed3d  jns     short loc_14000ED48
0x14000ed3f  lea     r9, aFailedToAlloca_3; "Failed to allocate string"
0x14000ed46  jmp     short loc_14000ED96
0x14000ed48  mov     rdi, [rsi+0D0h]
0x14000ed4f  lea     rcx, [rsi+0B8h]
0x14000ed56  mov     rdx, rdi
0x14000ed59  call    ?MakeRoomAt@?$CCbsArrayBase@ULocalSource@CCbsTiSession@@V?$CCbsArray@ULocalSource@CCbsTiSession@@@@@@IEAAJ_K@Z; CCbsArrayBase<CCbsTiSession::LocalSource,CCbsArray<CCbsTiSession::LocalSource>>::MakeRoomAt(unsigned __int64)
0x14000ed5e  mov     ebx, eax
0x14000ed60  test    eax, eax
0x14000ed62  js      short loc_14000ED8F
0x14000ed64  movups  xmm0, [rsp+88h+var_68]
0x14000ed69  mov     rax, [rsi+0E0h]
0x14000ed70  lea     rcx, [rsp+88h+var_68]; this
0x14000ed75  add     rdi, rdi
0x14000ed78  mov     qword ptr [rsp+88h+var_68+8], 0
0x14000ed81  movdqu  xmmword ptr [rax+rdi*8], xmm0
0x14000ed86  call    ??1LocalSource@CCbsTiSession@@QEAA@XZ; CCbsTiSession::LocalSource::~LocalSource(void)
0x14000ed8b  xor     ebx, ebx
0x14000ed8d  jmp     short loc_14000EDAF
0x14000ed8f  lea     r9, aFailedToAlloca_14; "Failed to allocate resource"
0x14000ed96  mov     r8d, r12d
0x14000ed99  mov     edx, eax
0x14000ed9b  mov     ecx, 4000000h
0x14000eda0  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14000eda5  lea     rcx, [rsp+88h+var_68]; this
0x14000edaa  call    ??1LocalSource@CCbsTiSession@@QEAA@XZ; CCbsTiSession::LocalSource::~LocalSource(void)
0x14000edaf  lea     rcx, [rsp+88h+var_58]; this
0x14000edb4  call    ??1CritSecLocker@@UEAA@XZ; CritSecLocker::~CritSecLocker(void)
0x14000edb9  mov     eax, ebx
0x14000edbb  add     rsp, 58h
0x14000edbf  pop     r14
0x14000edc1  pop     r12
0x14000edc3  pop     rdi
0x14000edc4  pop     rsi
0x14000edc5  pop     rbp
0x14000edc6  pop     rbx
0x14000edc7  retn
```
