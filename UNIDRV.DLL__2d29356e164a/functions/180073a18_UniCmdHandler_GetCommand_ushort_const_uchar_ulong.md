# UniCmdHandler::GetCommand(ushort const *,uchar * *,ulong *)

- ea: `0x180073a18`
- end: `0x180073bf6`
- name: `?GetCommand@UniCmdHandler@@QEAAJPEBGPEAPEAEPEAK@Z`
- size: `478`
- prototype: `__int64 __fastcall(UniCmdHandler *__hidden this, const unsigned __int16 *, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180073710`

## callees

- `0x18002c6bc`
- `0x180049128`
- `0x180073a18`
- `0x180073bfc`
- `0x1800741d0`
- `0x1800742c4`
- `0x180075010`

## import_xrefs

- `ole32!CreateStreamOnHGlobal` at `0x180073a5e`
- `ole32!CreateStreamOnHGlobal` at `0x180073a5e`

## pseudocode

```c
__int64 __fastcall UniCmdHandler::GetCommand(
        CPrintCoreConfig **this,
        const unsigned __int16 *a2,
        unsigned __int8 **a3,
        unsigned int *a4)
{
  HRESULT v8; // ebx
  int v9; // eax
  unsigned int i; // ebx
  __int64 v11; // rcx
  struct _COMMAND *v12; // rdx
  unsigned int v13; // eax
  unsigned __int8 *v14; // rax
  unsigned __int64 v16; // [rsp+30h] [rbp-10h] BYREF
  __int64 v17; // [rsp+80h] [rbp+40h] BYREF
  LPSTREAM ppstm; // [rsp+88h] [rbp+48h] BYREF

  *a4 = 0;
  *a3 = 0;
  ppstm = 0;
  v8 = CreateStreamOnHGlobal(0, 1, &ppstm);
  if ( v8 >= 0 )
  {
    LODWORD(v17) = 0;
    if ( UniCmdHandler::IsValidSeqCommandName((UniCmdHandler *)this, a2, (unsigned int *)&v17) )
    {
      v9 = UniCmdHandler::WriteSequenceCommandToStream((UniCmdHandler *)this, v17, ppstm);
    }
    else
    {
      for ( i = 0; ; ++i )
      {
        if ( i >= 0x5C )
        {
          v8 = -2147024809;
          goto LABEL_21;
        }
        if ( !wcsicmp((&off_18007A760)[2 * (int)i], a2) )
          break;
      }
      _mm_lfence();
      v11 = *(unsigned int *)(*((unsigned int *)*this + 2)
                            + 4LL * *((int *)&off_18007A760 + 4 * (int)i + 2)
                            + *((_QWORD *)*this + 13));
      if ( (_DWORD)v11 == -1 )
        v12 = 0;
      else
        v12 = (struct _COMMAND *)(*((_QWORD *)*this + 12) + *((unsigned int *)*this + 4) + 28 * v11);
      v9 = UniCmdHandler::WriteCommandToStream((UniCmdHandler *)this, v12, ppstm);
    }
    v8 = v9;
    if ( v9 >= 0 )
    {
      v16 = 0;
      v17 = 0;
      v8 = ((__int64 (__fastcall *)(LPSTREAM, _QWORD, __int64, unsigned __int64 *))ppstm->lpVtbl->Seek)(
             ppstm,
             0,
             1,
             &v16);
      if ( v8 >= 0 )
      {
        v8 = ((__int64 (__fastcall *)(LPSTREAM, __int64, _QWORD, _QWORD))ppstm->lpVtbl->Seek)(ppstm, v17, 0, 0);
        if ( v8 >= 0 )
        {
          v13 = v16;
          *a4 = v16;
          v14 = (unsigned __int8 *)CPrintCoreConfig::PrivateAlloc(this[63], v13);
          *a3 = v14;
          if ( v14 )
          {
            LODWORD(v17) = 0;
            v8 = ((__int64 (__fastcall *)(LPSTREAM, unsigned __int8 *, _QWORD, __int64 *))ppstm->lpVtbl->Read)(
                   ppstm,
                   v14,
                   (unsigned int)v16,
                   &v17);
            if ( v8 >= 0 && (_DWORD)v17 != (_DWORD)v16 )
              v8 = -2147467260;
          }
          else
          {
            v8 = -2147024882;
          }
        }
      }
    }
LABEL_21:
    ((void (__fastcall *)(LPSTREAM))ppstm->lpVtbl->Release)(ppstm);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180073a18  mov     [rsp-28h+arg_0], rbx
0x180073a1d  mov     [rsp-28h+arg_8], rsi
0x180073a22  push    rbp
0x180073a23  push    rdi
0x180073a24  push    r12
0x180073a26  push    r14
0x180073a28  push    r15
0x180073a2a  mov     rbp, rsp
0x180073a2d  sub     rsp, 40h
0x180073a31  mov     dword ptr [r9], 0
0x180073a38  mov     r12, r8
0x180073a3b  mov     qword ptr [r8], 0
0x180073a42  mov     r14, rdx
0x180073a45  mov     rdi, rcx
0x180073a48  mov     [rbp+ppstm], 0
0x180073a50  lea     r8, [rbp+ppstm]; ppstm
0x180073a54  mov     edx, 1; fDeleteOnRelease
0x180073a59  xor     ecx, ecx; hGlobal
0x180073a5b  mov     r15, r9
0x180073a5e  call    cs:__imp_CreateStreamOnHGlobal
0x180073a64  mov     ebx, eax
0x180073a66  test    eax, eax
0x180073a68  js      loc_180073BDD
0x180073a6e  lea     r8, [rbp+arg_10]; unsigned int *
0x180073a72  mov     dword ptr [rbp+arg_10], 0
0x180073a79  mov     rdx, r14; unsigned __int16 *
0x180073a7c  mov     rcx, rdi; this
0x180073a7f  call    ?IsValidSeqCommandName@UniCmdHandler@@AEAA_NPEBGPEAK@Z; UniCmdHandler::IsValidSeqCommandName(ushort const *,ulong *)
0x180073a84  test    al, al
0x180073a86  jz      short loc_180073A99
0x180073a88  mov     r8, [rbp+ppstm]; struct IStream *
0x180073a8c  mov     rcx, rdi; this
0x180073a8f  mov     edx, dword ptr [rbp+arg_10]; unsigned int
0x180073a92  call    ?WriteSequenceCommandToStream@UniCmdHandler@@AEAAJKPEAUIStream@@@Z; UniCmdHandler::WriteSequenceCommandToStream(ulong,IStream *)
0x180073a97  jmp     short loc_180073B0A
0x180073a99  xor     ebx, ebx
0x180073a9b  lea     rax, off_18007A760; "CmdCopies"
0x180073aa2  cmp     ebx, 5Ch ; '\'
0x180073aa5  jnb     loc_180073BC8
0x180073aab  movsxd  rsi, ebx
0x180073aae  mov     rdx, r14; String2
0x180073ab1  add     rsi, rsi
0x180073ab4  mov     rcx, [rax+rsi*8]; String1
0x180073ab8  call    _wcsicmp
0x180073abd  test    eax, eax
0x180073abf  lea     rax, off_18007A760; "CmdCopies"
0x180073ac6  jz      short loc_180073ACC
0x180073ac8  inc     ebx
0x180073aca  jmp     short loc_180073AA2
0x180073acc  lfence
0x180073acf  movsxd  rcx, dword ptr [rax+rsi*8+8]
0x180073ad4  mov     r8, [rdi]
0x180073ad7  mov     eax, [r8+8]
0x180073adb  lea     rdx, [rax+rcx*4]
0x180073adf  mov     rax, [r8+68h]
0x180073ae3  mov     ecx, [rdx+rax]
0x180073ae6  cmp     ecx, 0FFFFFFFFh
0x180073ae9  jnz     short loc_180073AEF
0x180073aeb  xor     edx, edx
0x180073aed  jmp     short loc_180073AFE
0x180073aef  mov     eax, [r8+10h]
0x180073af3  imul    rdx, rcx, 1Ch
0x180073af7  add     rdx, rax
0x180073afa  add     rdx, [r8+60h]; struct _COMMAND *
0x180073afe  mov     r8, [rbp+ppstm]; struct IStream *
0x180073b02  mov     rcx, rdi; this
0x180073b05  call    ?WriteCommandToStream@UniCmdHandler@@AEAAJPEAU_COMMAND@@PEAUIStream@@@Z; UniCmdHandler::WriteCommandToStream(_COMMAND *,IStream *)
0x180073b0a  mov     ebx, eax
0x180073b0c  test    eax, eax
0x180073b0e  js      loc_180073BCD
0x180073b14  mov     rcx, [rbp+ppstm]
0x180073b18  lea     r9, [rbp+var_10]
0x180073b1c  mov     [rbp+var_10], 0
0x180073b24  mov     r8d, 1
0x180073b2a  mov     [rbp+arg_10], 0
0x180073b32  mov     rdx, [rbp+arg_10]
0x180073b36  mov     rax, [rcx]
0x180073b39  mov     rax, [rax+28h]
0x180073b3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073b42  mov     ebx, eax
0x180073b44  test    eax, eax
0x180073b46  js      loc_180073BCD
0x180073b4c  mov     rcx, [rbp+ppstm]
0x180073b50  xor     r9d, r9d
0x180073b53  mov     rdx, [rbp+arg_10]
0x180073b57  xor     r8d, r8d
0x180073b5a  mov     rax, [rcx]
0x180073b5d  mov     rax, [rax+28h]
0x180073b61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073b66  mov     ebx, eax
0x180073b68  test    eax, eax
0x180073b6a  js      short loc_180073BCD
0x180073b6c  mov     rax, [rbp+var_10]
0x180073b70  mov     [r15], eax
0x180073b73  mov     rcx, [rdi+1F8h]; this
0x180073b7a  mov     edx, eax; unsigned __int64
0x180073b7c  call    ?PrivateAlloc@CPrintCoreConfig@@QEAAPEAX_K@Z; CPrintCoreConfig::PrivateAlloc(unsigned __int64)
0x180073b81  mov     [r12], rax
0x180073b85  mov     rdx, rax
0x180073b88  test    rax, rax
0x180073b8b  jnz     short loc_180073B94
0x180073b8d  mov     ebx, 8007000Eh
0x180073b92  jmp     short loc_180073BCD
0x180073b94  mov     rcx, [rbp+ppstm]
0x180073b98  lea     r9, [rbp+arg_10]
0x180073b9c  mov     r8d, dword ptr [rbp+var_10]
0x180073ba0  mov     dword ptr [rbp+arg_10], 0
0x180073ba7  mov     rax, [rcx]
0x180073baa  mov     rax, [rax+18h]
0x180073bae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073bb3  mov     ebx, eax
0x180073bb5  test    eax, eax
0x180073bb7  js      short loc_180073BCD
0x180073bb9  mov     eax, dword ptr [rbp+var_10]
0x180073bbc  cmp     dword ptr [rbp+arg_10], eax
0x180073bbf  jz      short loc_180073BCD
0x180073bc1  mov     ebx, 80004004h
0x180073bc6  jmp     short loc_180073BCD
0x180073bc8  mov     ebx, 80070057h
0x180073bcd  mov     rcx, [rbp+ppstm]
0x180073bd1  mov     rax, [rcx]
0x180073bd4  mov     rax, [rax+10h]
0x180073bd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073bdd  mov     rsi, [rsp+40h+arg_8]
0x180073be2  mov     eax, ebx
0x180073be4  mov     rbx, [rsp+40h+arg_0]
0x180073be9  add     rsp, 40h
0x180073bed  pop     r15
0x180073bef  pop     r14
0x180073bf1  pop     r12
0x180073bf3  pop     rdi
0x180073bf4  pop     rbp
0x180073bf5  retn
```
