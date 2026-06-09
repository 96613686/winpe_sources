# UniCmdHandler::GetCommand(ushort const *,uchar * *,ulong *)

- ea: `0x180075ae8`
- end: `0x180075ccd`
- name: `?GetCommand@UniCmdHandler@@QEAAJPEBGPEAPEAEPEAK@Z`
- size: `485`
- prototype: `__int64 __fastcall(CPrintCoreConfig **this, const unsigned __int16 *, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800757e0`

## callees

- `0x18002cf24`
- `0x18004a668`
- `0x180075ae8`
- `0x180075cd4`
- `0x1800762ac`
- `0x1800763a0`
- `0x180077010`

## import_xrefs

- `ole32!CreateStreamOnHGlobal` at `0x180075b2e`
- `ole32!CreateStreamOnHGlobal` at `0x180075b2e`

## pseudocode

```c
__int64 __fastcall UniCmdHandler::GetCommand(
        CPrintCoreConfig **this,
        const unsigned __int16 *a2,
        unsigned __int8 **a3,
        unsigned int *a4)
{
  HRESULT v8; // ebx
  HRESULT v9; // eax
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
        if ( !wcsicmp((&off_18007C760)[2 * (int)i], a2) )
          break;
      }
      _mm_lfence();
      v11 = *(unsigned int *)(*((unsigned int *)*this + 2)
                            + 4LL * *((int *)&off_18007C760 + 4 * (int)i + 2)
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
0x180075ae8  mov     [rsp-28h+arg_0], rbx
0x180075aed  mov     [rsp-28h+arg_8], rsi
0x180075af2  push    rbp
0x180075af3  push    rdi
0x180075af4  push    r12
0x180075af6  push    r14
0x180075af8  push    r15
0x180075afa  mov     rbp, rsp
0x180075afd  sub     rsp, 40h
0x180075b01  mov     dword ptr [r9], 0
0x180075b08  mov     r12, r8
0x180075b0b  mov     qword ptr [r8], 0
0x180075b12  mov     r14, rdx
0x180075b15  mov     rdi, rcx
0x180075b18  mov     [rbp+ppstm], 0
0x180075b20  lea     r8, [rbp+ppstm]; ppstm
0x180075b24  mov     edx, 1; fDeleteOnRelease
0x180075b29  xor     ecx, ecx; hGlobal
0x180075b2b  mov     r15, r9
0x180075b2e  call    cs:__imp_CreateStreamOnHGlobal
0x180075b35  nop     dword ptr [rax+rax+00h]
0x180075b3a  mov     ebx, eax
0x180075b3c  test    eax, eax
0x180075b3e  js      loc_180075CB3
0x180075b44  lea     r8, [rbp+arg_10]; unsigned int *
0x180075b48  mov     dword ptr [rbp+arg_10], 0
0x180075b4f  mov     rdx, r14; unsigned __int16 *
0x180075b52  mov     rcx, rdi; this
0x180075b55  call    ?IsValidSeqCommandName@UniCmdHandler@@AEAA_NPEBGPEAK@Z; UniCmdHandler::IsValidSeqCommandName(ushort const *,ulong *)
0x180075b5a  test    al, al
0x180075b5c  jz      short loc_180075B6F
0x180075b5e  mov     r8, [rbp+ppstm]; struct IStream *
0x180075b62  mov     rcx, rdi; this
0x180075b65  mov     edx, dword ptr [rbp+arg_10]; unsigned int
0x180075b68  call    ?WriteSequenceCommandToStream@UniCmdHandler@@AEAAJKPEAUIStream@@@Z; UniCmdHandler::WriteSequenceCommandToStream(ulong,IStream *)
0x180075b6d  jmp     short loc_180075BE0
0x180075b6f  xor     ebx, ebx
0x180075b71  lea     rax, off_18007C760; "CmdCopies"
0x180075b78  cmp     ebx, 5Ch ; '\'
0x180075b7b  jnb     loc_180075C9E
0x180075b81  movsxd  rsi, ebx
0x180075b84  mov     rdx, r14; String2
0x180075b87  add     rsi, rsi
0x180075b8a  mov     rcx, [rax+rsi*8]; String1
0x180075b8e  call    _wcsicmp
0x180075b93  test    eax, eax
0x180075b95  lea     rax, off_18007C760; "CmdCopies"
0x180075b9c  jz      short loc_180075BA2
0x180075b9e  inc     ebx
0x180075ba0  jmp     short loc_180075B78
0x180075ba2  lfence
0x180075ba5  movsxd  rcx, dword ptr [rax+rsi*8+8]
0x180075baa  mov     r8, [rdi]
0x180075bad  mov     eax, [r8+8]
0x180075bb1  lea     rdx, [rax+rcx*4]
0x180075bb5  mov     rax, [r8+68h]
0x180075bb9  mov     ecx, [rdx+rax]
0x180075bbc  cmp     ecx, 0FFFFFFFFh
0x180075bbf  jnz     short loc_180075BC5
0x180075bc1  xor     edx, edx
0x180075bc3  jmp     short loc_180075BD4
0x180075bc5  mov     eax, [r8+10h]
0x180075bc9  imul    rdx, rcx, 1Ch
0x180075bcd  add     rdx, rax
0x180075bd0  add     rdx, [r8+60h]; struct _COMMAND *
0x180075bd4  mov     r8, [rbp+ppstm]; struct IStream *
0x180075bd8  mov     rcx, rdi; this
0x180075bdb  call    ?WriteCommandToStream@UniCmdHandler@@AEAAJPEAU_COMMAND@@PEAUIStream@@@Z; UniCmdHandler::WriteCommandToStream(_COMMAND *,IStream *)
0x180075be0  mov     ebx, eax
0x180075be2  test    eax, eax
0x180075be4  js      loc_180075CA3
0x180075bea  mov     rcx, [rbp+ppstm]
0x180075bee  lea     r9, [rbp+var_10]
0x180075bf2  mov     [rbp+var_10], 0
0x180075bfa  mov     r8d, 1
0x180075c00  mov     [rbp+arg_10], 0
0x180075c08  mov     rdx, [rbp+arg_10]
0x180075c0c  mov     rax, [rcx]
0x180075c0f  mov     rax, [rax+28h]
0x180075c13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075c18  mov     ebx, eax
0x180075c1a  test    eax, eax
0x180075c1c  js      loc_180075CA3
0x180075c22  mov     rcx, [rbp+ppstm]
0x180075c26  xor     r9d, r9d
0x180075c29  mov     rdx, [rbp+arg_10]
0x180075c2d  xor     r8d, r8d
0x180075c30  mov     rax, [rcx]
0x180075c33  mov     rax, [rax+28h]
0x180075c37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075c3c  mov     ebx, eax
0x180075c3e  test    eax, eax
0x180075c40  js      short loc_180075CA3
0x180075c42  mov     rax, [rbp+var_10]
0x180075c46  mov     [r15], eax
0x180075c49  mov     rcx, [rdi+1F8h]; this
0x180075c50  mov     edx, eax; unsigned __int64
0x180075c52  call    ?PrivateAlloc@CPrintCoreConfig@@QEAAPEAX_K@Z; CPrintCoreConfig::PrivateAlloc(unsigned __int64)
0x180075c57  mov     [r12], rax
0x180075c5b  mov     rdx, rax
0x180075c5e  test    rax, rax
0x180075c61  jnz     short loc_180075C6A
0x180075c63  mov     ebx, 8007000Eh
0x180075c68  jmp     short loc_180075CA3
0x180075c6a  mov     rcx, [rbp+ppstm]
0x180075c6e  lea     r9, [rbp+arg_10]
0x180075c72  mov     r8d, dword ptr [rbp+var_10]
0x180075c76  mov     dword ptr [rbp+arg_10], 0
0x180075c7d  mov     rax, [rcx]
0x180075c80  mov     rax, [rax+18h]
0x180075c84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075c89  mov     ebx, eax
0x180075c8b  test    eax, eax
0x180075c8d  js      short loc_180075CA3
0x180075c8f  mov     eax, dword ptr [rbp+var_10]
0x180075c92  cmp     dword ptr [rbp+arg_10], eax
0x180075c95  jz      short loc_180075CA3
0x180075c97  mov     ebx, 80004004h
0x180075c9c  jmp     short loc_180075CA3
0x180075c9e  mov     ebx, 80070057h
0x180075ca3  mov     rcx, [rbp+ppstm]
0x180075ca7  mov     rax, [rcx]
0x180075caa  mov     rax, [rax+10h]
0x180075cae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075cb3  mov     rsi, [rsp+40h+arg_8]
0x180075cb8  mov     eax, ebx
0x180075cba  mov     rbx, [rsp+40h+arg_0]
0x180075cbf  add     rsp, 40h
0x180075cc3  pop     r15
0x180075cc5  pop     r14
0x180075cc7  pop     r12
0x180075cc9  pop     rdi
0x180075cca  pop     rbp
0x180075ccb  retn
```
