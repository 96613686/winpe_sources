# CCbsTiSession::GetStatus(uint *,_CbsSessionState *,int *,long *)

- ea: `0x1400100f4`
- end: `0x14001024b`
- name: `?GetStatus@CCbsTiSession@@UEAAJPEAIPEAW4_CbsSessionState@@PEAHPEAJ@Z`
- size: `343`
- prototype: `__int64 __fastcall(CCbsTiSession *__hidden this, unsigned int *, enum _CbsSessionState *, int *, int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1400100e0`

## callees

- `0x140006778`
- `0x14000e2ac`
- `0x1400100f4`
- `0x1400106c4`
- `0x140017658`
- `0x14002b010`

## string_xrefs

- `0x140010167`: `Invalid argument: pbComplete.`

## pseudocode

```c
__int64 __fastcall CCbsTiSession::GetStatus(
        CCbsTiSession *this,
        unsigned int *a2,
        enum _CbsSessionState *a3,
        int *a4,
        int *a5)
{
  CCbsTiSession *v5; // rbx
  unsigned int v10; // ebx
  __int64 v11; // rdx
  int *v12; // rax
  int v13; // ecx
  int v14; // edx
  int SureWorkerSessionAvailable; // eax
  const char *v16; // r9
  _BYTE v18[88]; // [rsp+30h] [rbp-58h] BYREF

  v5 = (CCbsTiSession *)((char *)this - 256);
  CritSecLocker::CritSecLocker((CritSecLocker *)v18, (CCbsTiSession *)((char *)this - 208), 1);
  if ( a2 )
  {
    if ( a3 )
    {
      if ( a4 )
      {
        if ( a5 )
        {
          v11 = *((_QWORD *)this - 21);
          if ( !v11
            || ((v12 = (int *)(v11 + 48), v13 = -2145116147, !*(_DWORD *)(v11 + 68)) || (v14 = 985091, *v12 != 985091))
            && (v14 = *v12, *v12 != -2145116147) )
          {
            SureWorkerSessionAvailable = CCbsTiSession::MakeSureWorkerSessionAvailable(v5, 1);
            v10 = SureWorkerSessionAvailable;
            if ( SureWorkerSessionAvailable >= 0 )
            {
              SureWorkerSessionAvailable = (*(__int64 (__fastcall **)(_QWORD, unsigned int *, enum _CbsSessionState *, int *, int *))(**((_QWORD **)this - 27) + 72LL))(
                                             *((_QWORD *)this - 27),
                                             a2,
                                             a3,
                                             a4,
                                             a5);
              v10 = SureWorkerSessionAvailable;
              if ( SureWorkerSessionAvailable >= 0 )
                goto LABEL_21;
              v16 = "Failed to GetStatus using worker session";
            }
            else
            {
              v16 = "Failed to get worker session.";
            }
            CBSWdsLogLight(0x4000000u, (unsigned int)SureWorkerSessionAvailable, (size_t *)1, v16);
            goto LABEL_21;
          }
          v10 = 0;
          if ( v14 != -2145116147 )
            v13 = 0;
          *a5 = v13;
          *a4 = 1;
          *(_DWORD *)a3 = 208;
          *a2 = 1;
        }
        else
        {
          v10 = -2147467261;
          CBSWdsLogLight(0x4000000u, 0x80004003, (size_t *)1, "Invalid argument: phrStatus.");
        }
      }
      else
      {
        v10 = -2147467261;
        CBSWdsLogLight(0x4000000u, 0x80004003, (size_t *)1, "Invalid argument: pbComplete.");
      }
    }
    else
    {
      v10 = -2147467261;
      CBSWdsLogLight(0x4000000u, 0x80004003, (size_t *)1, "Invalid argument: pLastSuccessfulSessionState.");
    }
  }
  else
  {
    v10 = -2147467261;
    CBSWdsLogLight(0x4000000u, 0x80004003, (size_t *)1, "Invalid argument: pCurrentPhase.");
  }
LABEL_21:
  CritSecLocker::~CritSecLocker((CritSecLocker *)v18);
  return v10;
}

```

## disassembly

```asm
0x1400100f4  push    rbx
0x1400100f6  push    rbp
0x1400100f7  push    rsi
0x1400100f8  push    rdi
0x1400100f9  push    r12
0x1400100fb  push    r14
0x1400100fd  push    r15
0x1400100ff  sub     rsp, 50h
0x140010103  lea     rbx, [rcx-100h]
0x14001010a  mov     r14, r8
0x14001010d  mov     r15, rdx
0x140010110  mov     rbp, rcx
0x140010113  mov     r12d, 1
0x140010119  lea     rdx, [rbx+30h]; struct AutoCritSec *
0x14001011d  mov     r8b, r12b; bool
0x140010120  lea     rcx, [rsp+88h+var_58]; this
0x140010125  mov     rsi, r9
0x140010128  call    ??0CritSecLocker@@QEAA@AEAVAutoCritSec@@_N@Z; CritSecLocker::CritSecLocker(AutoCritSec &,bool)
0x14001012d  test    r15, r15
0x140010130  jnz     short loc_140010145
0x140010132  mov     edx, 80004003h
0x140010137  lea     r9, aInvalidArgumen_24; "Invalid argument: pCurrentPhase."
0x14001013e  mov     ebx, edx
0x140010140  jmp     loc_140010223
0x140010145  test    r14, r14
0x140010148  jnz     short loc_14001015D
0x14001014a  mov     edx, 80004003h
0x14001014f  lea     r9, aInvalidArgumen_33; "Invalid argument: pLastSuccessfulSessio"...
0x140010156  mov     ebx, edx
0x140010158  jmp     loc_140010223
0x14001015d  test    rsi, rsi
0x140010160  jnz     short loc_140010175
0x140010162  mov     edx, 80004003h
0x140010167  lea     r9, aInvalidArgumen_12; "Invalid argument: pbComplete."
0x14001016e  mov     ebx, edx
0x140010170  jmp     loc_140010223
0x140010175  mov     rdi, [rsp+88h+arg_20]
0x14001017d  test    rdi, rdi
0x140010180  jnz     short loc_140010195
0x140010182  mov     edx, 80004003h
0x140010187  lea     r9, aInvalidArgumen_8; "Invalid argument: phrStatus."
0x14001018e  mov     ebx, edx
0x140010190  jmp     loc_140010223
0x140010195  mov     rdx, [rbp-0A8h]
0x14001019c  test    rdx, rdx
0x14001019f  jz      short loc_1400101D9
0x1400101a1  cmp     dword ptr [rdx+44h], 0
0x1400101a5  lea     rax, [rdx+30h]
0x1400101a9  mov     ecx, 8024200Dh
0x1400101ae  jz      short loc_1400101B9
0x1400101b0  mov     edx, 0F0803h
0x1400101b5  cmp     [rax], edx
0x1400101b7  jz      short loc_1400101BF
0x1400101b9  mov     edx, [rax]
0x1400101bb  cmp     edx, ecx
0x1400101bd  jnz     short loc_1400101D9
0x1400101bf  xor     eax, eax
0x1400101c1  xor     ebx, ebx
0x1400101c3  cmp     edx, ecx
0x1400101c5  cmovnz  ecx, eax
0x1400101c8  mov     [rdi], ecx
0x1400101ca  mov     [rsi], r12d
0x1400101cd  mov     dword ptr [r14], 0D0h
0x1400101d4  mov     [r15], r12d
0x1400101d7  jmp     short loc_140010230
0x1400101d9  mov     dl, r12b; bool
0x1400101dc  mov     rcx, rbx; this
0x1400101df  call    ?MakeSureWorkerSessionAvailable@CCbsTiSession@@QEAAJ_N@Z; CCbsTiSession::MakeSureWorkerSessionAvailable(bool)
0x1400101e4  mov     ebx, eax
0x1400101e6  test    eax, eax
0x1400101e8  jns     short loc_1400101F3
0x1400101ea  lea     r9, aFailedToGetWor_1; "Failed to get worker session."
0x1400101f1  jmp     short loc_140010221
0x1400101f3  mov     rcx, [rbp-0D8h]
0x1400101fa  mov     r9, rsi
0x1400101fd  mov     r8, r14
0x140010200  mov     [rsp+88h+var_68], rdi
0x140010205  mov     rdx, r15
0x140010208  mov     rax, [rcx]
0x14001020b  mov     rax, [rax+48h]
0x14001020f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010214  mov     ebx, eax
0x140010216  test    eax, eax
0x140010218  jns     short loc_140010230
0x14001021a  lea     r9, aFailedToGetsta; "Failed to GetStatus using worker sessio"...
0x140010221  mov     edx, eax
0x140010223  mov     r8d, r12d
0x140010226  mov     ecx, 4000000h
0x14001022b  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x140010230  lea     rcx, [rsp+88h+var_58]; this
0x140010235  call    ??1CritSecLocker@@UEAA@XZ; CritSecLocker::~CritSecLocker(void)
0x14001023a  mov     eax, ebx
0x14001023c  add     rsp, 50h
0x140010240  pop     r15
0x140010242  pop     r14
0x140010244  pop     r12
0x140010246  pop     rdi
0x140010247  pop     rsi
0x140010248  pop     rbp
0x140010249  pop     rbx
0x14001024a  retn
```
