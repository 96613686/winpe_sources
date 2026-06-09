# CBinaryRuleReader::ConvertDataFormatOnRead(DataFormats,tagPROPVARIANT *)

- ea: `0x18000fc60`
- end: `0x18000fd76`
- name: `?ConvertDataFormatOnRead@CBinaryRuleReader@@UEAAJW4DataFormats@@PEAUtagPROPVARIANT@@@Z`
- size: `278`
- prototype: `int __high(enum DataFormats, struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000fc60`
- `0x1800132dc`
- `0x180017ec4`
- `0x180017f30`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18000fcf5`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18000fd26`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18000fcf5`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18000fd26`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000fcc9`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000fcc9`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CBinaryRuleReader::ConvertDataFormatOnRead(__int64 a1, int a2, struct tagPROPVARIANT *a3)
{
  unsigned int v4; // ebx
  int v6; // eax
  PROPVARIANT pvar; // [rsp+20h] [rbp-20h] BYREF

  v4 = 0;
  if ( a2 != 11 )
  {
    if ( a2 != 17 )
      return v4;
    memset(&pvar, 0, sizeof(pvar));
    v6 = PropVariantCopy(&pvar, a3);
    v4 = v6;
    if ( v6 >= 0 && (v6 = CBinaryRuleReader::ConvertXMPGPSVersionToBuffer(&pvar, a3), v4 = v6, v6 >= 0)
      || !g_doStackCaptures )
    {
LABEL_9:
      PropVariantClear(&pvar);
      return v4;
    }
LABEL_8:
    DoStackCapture(v6);
    goto LABEL_9;
  }
  if ( a3->vt == 65 )
  {
    memset(&pvar, 0, sizeof(pvar));
    v6 = PropVariantCopy(&pvar, a3);
    v4 = v6;
    if ( v6 >= 0 )
    {
      v6 = CBinaryRuleReader::ConvertFromBlobToBuffer(&pvar, a3);
      v4 = v6;
      if ( v6 >= 0 )
        goto LABEL_9;
    }
    if ( !g_doStackCaptures )
      goto LABEL_9;
    goto LABEL_8;
  }
  if ( a3->vt != 4113 )
  {
    v4 = -2003292274;
    if ( g_doStackCaptures )
      DoStackCapture(-2003292274);
  }
  return v4;
}

```

## disassembly

```asm
0x18000fc60  mov     [rsp-8+arg_0], rbx
0x18000fc65  mov     [rsp-8+arg_8], rdi
0x18000fc6a  push    rbp
0x18000fc6b  mov     rbp, rsp
0x18000fc6e  sub     rsp, 40h
0x18000fc72  mov     rdi, r8
0x18000fc75  xor     ebx, ebx
0x18000fc77  cmp     edx, 0Bh
0x18000fc7a  jz      short loc_18000FC94
0x18000fc7c  cmp     edx, 11h
0x18000fc7f  jz      short loc_18000FCE1
0x18000fc81  mov     eax, ebx
0x18000fc83  mov     rbx, [rsp+40h+arg_0]
0x18000fc88  mov     rdi, [rsp+40h+arg_8]
0x18000fc8d  add     rsp, 40h
0x18000fc91  pop     rbp
0x18000fc92  retn
0x18000fc94  cmp     word ptr [r8], 41h ; 'A'
0x18000fc99  jz      short loc_18000FD12
0x18000fc9b  mov     eax, 1011h
0x18000fca0  cmp     [r8], ax
0x18000fca4  jz      short loc_18000FC81
0x18000fca6  mov     ebx, 88982F8Eh
0x18000fcab  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18000fcb2  jz      short loc_18000FC81
0x18000fcb4  mov     ecx, ebx; int
0x18000fcb6  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18000fcbb  jmp     short loc_18000FC81
0x18000fcbd  mov     ecx, eax; int
0x18000fcbf  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18000fcc4  nop
0x18000fcc5  lea     rcx, [rbp+pvar]; pvar
0x18000fcc9  call    cs:__imp_PropVariantClear
0x18000fcd0  nop     dword ptr [rax+rax+00h]
0x18000fcd5  jmp     short loc_18000FC81
0x18000fcd7  mov     ecx, eax; int
0x18000fcd9  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18000fcde  nop
0x18000fcdf  jmp     short loc_18000FCC5
0x18000fce1  xorps   xmm0, xmm0
0x18000fce4  xor     eax, eax
0x18000fce6  movups  xmmword ptr [rbp+pvar], xmm0
0x18000fcea  mov     qword ptr [rbp+pvar+10h], rax
0x18000fcee  mov     rdx, rdi; pvarSrc
0x18000fcf1  lea     rcx, [rbp+pvar]; pvarDest
0x18000fcf5  call    cs:__imp_PropVariantCopy
0x18000fcfc  nop     dword ptr [rax+rax+00h]
0x18000fd01  mov     ebx, eax
0x18000fd03  test    eax, eax
0x18000fd05  jns     short loc_18000FD4A
0x18000fd07  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18000fd0e  jnz     short loc_18000FCD7
0x18000fd10  jmp     short loc_18000FCDF
0x18000fd12  xorps   xmm0, xmm0
0x18000fd15  xor     eax, eax
0x18000fd17  movups  xmmword ptr [rbp+pvar], xmm0
0x18000fd1b  mov     qword ptr [rbp+pvar+10h], rax
0x18000fd1f  mov     rdx, rdi; pvarSrc
0x18000fd22  lea     rcx, [rbp+pvar]; pvarDest
0x18000fd26  call    cs:__imp_PropVariantCopy
0x18000fd2d  nop     dword ptr [rax+rax+00h]
0x18000fd32  mov     ebx, eax
0x18000fd34  test    eax, eax
0x18000fd36  jns     short loc_18000FD5E
0x18000fd38  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18000fd3f  jnz     loc_18000FCBD
0x18000fd45  jmp     loc_18000FCC5
0x18000fd4a  mov     rdx, rdi; struct tagPROPVARIANT *
0x18000fd4d  lea     rcx, [rbp+pvar]; struct tagPROPVARIANT *
0x18000fd51  call    ?ConvertXMPGPSVersionToBuffer@CBinaryRuleReader@@CAJPEAUtagPROPVARIANT@@0@Z; CBinaryRuleReader::ConvertXMPGPSVersionToBuffer(tagPROPVARIANT *,tagPROPVARIANT *)
0x18000fd56  mov     ebx, eax
0x18000fd58  test    eax, eax
0x18000fd5a  js      short loc_18000FD07
0x18000fd5c  jmp     short loc_18000FCDF
0x18000fd5e  mov     rdx, rdi; struct tagPROPVARIANT *
0x18000fd61  lea     rcx, [rbp+pvar]; struct tagPROPVARIANT *
0x18000fd65  call    ?ConvertFromBlobToBuffer@CBinaryRuleReader@@CAJPEBUtagPROPVARIANT@@PEAU2@@Z; CBinaryRuleReader::ConvertFromBlobToBuffer(tagPROPVARIANT const *,tagPROPVARIANT *)
0x18000fd6a  mov     ebx, eax
0x18000fd6c  test    eax, eax
0x18000fd6e  js      short loc_18000FD38
0x18000fd70  jmp     loc_18000FCC5
```
