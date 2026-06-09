# PrjfCopyFileBasicInformation

- ea: `0x14003875c`
- end: `0x1400389e5`
- name: `PrjfCopyFileBasicInformation`
- size: `649`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x14002e1a4`
- `0x1400389ec`

## callees

- `0x14000ba20`
- `0x14000d128`
- `0x14003875c`

## import_xrefs

- `FLTMGR!FltSetInformationFile` at `0x1400387f0`
- `FLTMGR!FltSetInformationFile` at `0x1400387f0`
- `FLTMGR!FltFsControlFile` at `0x14003889e`
- `FLTMGR!FltFsControlFile` at `0x140038958`
- `FLTMGR!FltFsControlFile` at `0x14003889e`
- `FLTMGR!FltFsControlFile` at `0x140038958`

## pseudocode

```c
__int64 __fastcall PrjfCopyFileBasicInformation(
        __int128 *a1,
        struct _FILE_OBJECT *a2,
        struct _FLT_INSTANCE *a3,
        char a4)
{
  __int128 v4; // xmm0
  __int128 v7; // xmm1
  int v8; // edi
  int v9; // ecx
  NTSTATUS v10; // eax
  int v11; // edx
  int v12; // r8d
  unsigned int v13; // ebx
  NTSTATUS v14; // eax
  int v15; // edx
  int v16; // r8d
  NTSTATUS v17; // eax
  int v18; // edx
  int v19; // r8d
  __int16 InputBuffer; // [rsp+60h] [rbp-19h] BYREF
  __int128 FileInformation; // [rsp+68h] [rbp-11h] BYREF
  __int128 v23; // [rsp+78h] [rbp-1h]
  __int64 v24; // [rsp+88h] [rbp+Fh]

  v4 = *a1;
  InputBuffer = 0;
  v7 = a1[1];
  FileInformation = v4;
  v24 = *((_QWORD *)a1 + 4);
  v23 = v7;
  if ( (a4 & 8) == 0 )
  {
    FileInformation = 0;
    v23 = 0;
  }
  v8 = a4 & 0x20;
  v9 = v8 != 0 ? v24 : 0;
  LODWORD(v24) = v9;
  if ( (a4 & 0x40) != 0 )
    LODWORD(v24) = v9 | 0x400000;
  v10 = FltSetInformationFile(a3, a2, &FileInformation, 0x28u, FileBasicInformation);
  v13 = v10;
  if ( v10 >= 0 )
  {
    if ( v8 && (v24 & 0x800) != 0 )
    {
      v14 = FltFsControlFile(a3, a2, 0x9003Cu, 0, 0, &InputBuffer, 2u, 0);
      if ( v14 < 0 )
      {
        if ( SBYTE1(xmmword_14001A3D0) < 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v15) = BYTE1(xmmword_14001A3D0) & 0x80;
          LOBYTE(v16) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          WPP_RECORDER_AND_TRACE_SF_sDL(
            527,
            v15,
            v16,
            *((_QWORD *)WPP_GLOBAL_Control + 8),
            2,
            15,
            45,
            (__int64)WPP_f518d8db80f83e9c1a62003295e898de_Traceguids,
            (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\utils.c",
            130,
            v14);
        }
        InputBuffer = 1;
      }
      v17 = FltFsControlFile(a3, a2, 0x9C040u, &InputBuffer, 2u, 0, 0, 0);
      v13 = v17;
      if ( v17 < 0
        && (SBYTE1(xmmword_14001A3D0) < 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED) )
      {
        LOBYTE(v18) = BYTE1(xmmword_14001A3D0) & 0x80;
        LOBYTE(v19) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sDL(
          527,
          v18,
          v19,
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          2,
          15,
          46,
          (__int64)WPP_f518d8db80f83e9c1a62003295e898de_Traceguids,
          (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\utils.c",
          147,
          v17);
      }
    }
  }
  else if ( SBYTE1(xmmword_14001A3D0) < 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v11) = BYTE1(xmmword_14001A3D0) & 0x80;
    LOBYTE(v12) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_sDL(
      527,
      v11,
      v12,
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      2,
      15,
      44,
      (__int64)WPP_f518d8db80f83e9c1a62003295e898de_Traceguids,
      (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\utils.c",
      104,
      v10);
  }
  return v13;
}

```

## disassembly

```asm
0x14003875c  push    rbp
0x14003875e  push    rbx
0x14003875f  push    rsi
0x140038760  push    rdi
0x140038761  push    r12
0x140038763  push    r14
0x140038765  push    r15
0x140038767  lea     rbp, [rsp-27h]
0x14003876c  sub     rsp, 0A0h
0x140038773  mov     rax, cs:__security_cookie
0x14003877a  xor     rax, rsp
0x14003877d  mov     [rbp+57h+var_40], rax
0x140038781  movups  xmm0, xmmword ptr [rcx]
0x140038784  xor     eax, eax
0x140038786  mov     r12, r8
0x140038789  mov     [rbp+57h+InputBuffer], ax
0x14003878d  mov     r15, rdx
0x140038790  movups  xmm1, xmmword ptr [rcx+10h]
0x140038794  movups  [rbp+57h+FileInformation], xmm0
0x140038798  movsd   xmm0, qword ptr [rcx+20h]
0x14003879d  movsd   [rbp+57h+var_48], xmm0
0x1400387a2  movups  [rbp+57h+var_58], xmm1
0x1400387a6  test    r9b, 8
0x1400387aa  jnz     short loc_1400387BC
0x1400387ac  xorps   xmm0, xmm0
0x1400387af  xorps   xmm1, xmm1
0x1400387b2  movdqu  [rbp+57h+FileInformation], xmm0
0x1400387b7  movdqu  [rbp+57h+var_58], xmm1
0x1400387bc  mov     edi, r9d
0x1400387bf  and     edi, 20h
0x1400387c2  mov     eax, edi
0x1400387c4  neg     eax
0x1400387c6  sbb     ecx, ecx
0x1400387c8  and     ecx, dword ptr [rbp+57h+var_48]
0x1400387cb  mov     dword ptr [rbp+57h+var_48], ecx
0x1400387ce  test    r9b, 40h
0x1400387d2  jz      short loc_1400387DB
0x1400387d4  bts     ecx, 16h
0x1400387d8  mov     dword ptr [rbp+57h+var_48], ecx
0x1400387db  mov     r9d, 28h ; '('; Length
0x1400387e1  mov     [rsp+0D0h+FileInformationClass], 4; FileInformationClass
0x1400387e9  lea     r8, [rbp+57h+FileInformation]; FileInformation
0x1400387ed  mov     rcx, r12; Instance
0x1400387f0  call    cs:__imp_FltSetInformationFile
0x1400387f7  nop     dword ptr [rax+rax+00h]
0x1400387fc  mov     ebx, eax
0x1400387fe  test    eax, eax
0x140038800  jns     short loc_140038858
0x140038802  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x140038808  lea     rdi, WPP_RECORDER_INITIALIZED
0x14003880f  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140038816  setnz   r8b
0x14003881a  and     dl, 80h
0x14003881d  jnz     short loc_140038828
0x14003881f  test    r8b, r8b
0x140038822  jz      loc_1400389C4
0x140038828  mov     [rsp+0D0h+var_80], eax
0x14003882c  lea     rsi, aOnecoreBaseFsG_2; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140038833  mov     [rsp+0D0h+var_88], 668h
0x14003883b  lea     r14, WPP_f518d8db80f83e9c1a62003295e898de_Traceguids
0x140038842  mov     [rsp+0D0h+var_90], rsi
0x140038847  mov     [rsp+0D0h+LengthReturned], r14
0x14003884c  mov     word ptr [rsp+0D0h+OutputBufferLength], 2Ch ; ','
0x140038853  jmp     loc_1400389A2
0x140038858  test    edi, edi
0x14003885a  jz      loc_1400389C4
0x140038860  test    dword ptr [rbp+57h+var_48], 800h
0x140038867  jz      loc_1400389C4
0x14003886d  mov     [rsp+0D0h+LengthReturned], 0; LengthReturned
0x140038876  lea     rax, [rbp+57h+InputBuffer]
0x14003887a  mov     [rsp+0D0h+OutputBufferLength], 2; OutputBufferLength
0x140038882  xor     r9d, r9d; InputBuffer
0x140038885  mov     [rsp+0D0h+OutputBuffer], rax; OutputBuffer
0x14003888a  mov     r8d, 9003Ch; FsControlCode
0x140038890  mov     rdx, r15; FileObject
0x140038893  mov     [rsp+0D0h+FileInformationClass], 0; InputBufferLength
0x14003889b  mov     rcx, r12; Instance
0x14003889e  call    cs:__imp_FltFsControlFile
0x1400388a5  nop     dword ptr [rax+rax+00h]
0x1400388aa  lea     rdi, WPP_RECORDER_INITIALIZED
0x1400388b1  lea     rsi, aOnecoreBaseFsG_2; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x1400388b8  lea     r14, WPP_f518d8db80f83e9c1a62003295e898de_Traceguids
0x1400388bf  test    eax, eax
0x1400388c1  jns     short loc_140038926
0x1400388c3  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x1400388ca  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x1400388d0  setnz   r8b
0x1400388d4  and     dl, 80h
0x1400388d7  jnz     short loc_1400388DE
0x1400388d9  test    r8b, r8b
0x1400388dc  jz      short loc_14003891D
0x1400388de  mov     r9, cs:WPP_GLOBAL_Control
0x1400388e5  mov     ecx, 20Fh
0x1400388ea  mov     [rsp+0D0h+var_80], eax
0x1400388ee  mov     [rsp+0D0h+var_88], 682h
0x1400388f6  mov     [rsp+0D0h+var_90], rsi
0x1400388fb  mov     r9, [r9+40h]
0x1400388ff  mov     [rsp+0D0h+LengthReturned], r14
0x140038904  mov     word ptr [rsp+0D0h+OutputBufferLength], 2Dh ; '-'
0x14003890b  mov     dword ptr [rsp+0D0h+OutputBuffer], 0Fh
0x140038913  mov     byte ptr [rsp+0D0h+FileInformationClass], 2
0x140038918  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x14003891d  mov     eax, 1
0x140038922  mov     [rbp+57h+InputBuffer], ax
0x140038926  mov     [rsp+0D0h+LengthReturned], 0; LengthReturned
0x14003892f  lea     r9, [rbp+57h+InputBuffer]; InputBuffer
0x140038933  mov     [rsp+0D0h+OutputBufferLength], 0; OutputBufferLength
0x14003893b  mov     r8d, 9C040h; FsControlCode
0x140038941  mov     [rsp+0D0h+OutputBuffer], 0; OutputBuffer
0x14003894a  mov     rdx, r15; FileObject
0x14003894d  mov     rcx, r12; Instance
0x140038950  mov     [rsp+0D0h+FileInformationClass], 2; InputBufferLength
0x140038958  call    cs:__imp_FltFsControlFile
0x14003895f  nop     dword ptr [rax+rax+00h]
0x140038964  mov     ebx, eax
0x140038966  test    eax, eax
0x140038968  jns     short loc_1400389C4
0x14003896a  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140038971  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x140038977  setnz   r8b
0x14003897b  and     dl, 80h
0x14003897e  jnz     short loc_140038985
0x140038980  test    r8b, r8b
0x140038983  jz      short loc_1400389C4
0x140038985  mov     [rsp+0D0h+var_80], eax
0x140038989  mov     [rsp+0D0h+var_88], 693h
0x140038991  mov     [rsp+0D0h+var_90], rsi
0x140038996  mov     [rsp+0D0h+LengthReturned], r14
0x14003899b  mov     word ptr [rsp+0D0h+OutputBufferLength], 2Eh ; '.'
0x1400389a2  mov     r9, cs:WPP_GLOBAL_Control
0x1400389a9  mov     ecx, 20Fh
0x1400389ae  mov     dword ptr [rsp+0D0h+OutputBuffer], 0Fh
0x1400389b6  mov     byte ptr [rsp+0D0h+FileInformationClass], 2
0x1400389bb  mov     r9, [r9+40h]
0x1400389bf  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x1400389c4  mov     eax, ebx
0x1400389c6  mov     rcx, [rbp+57h+var_40]
0x1400389ca  xor     rcx, rsp; StackCookie
0x1400389cd  call    __security_check_cookie
0x1400389d2  add     rsp, 0A0h
0x1400389d9  pop     r15
0x1400389db  pop     r14
0x1400389dd  pop     r12
0x1400389df  pop     rdi
0x1400389e0  pop     rsi
0x1400389e1  pop     rbx
0x1400389e2  pop     rbp
0x1400389e3  retn
```
