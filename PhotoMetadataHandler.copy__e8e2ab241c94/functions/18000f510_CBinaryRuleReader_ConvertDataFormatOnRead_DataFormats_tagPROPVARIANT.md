# CBinaryRuleReader::ConvertDataFormatOnRead(DataFormats,tagPROPVARIANT *)

- ea: `0x18000f510`
- end: `0x18000f60c`
- name: `?ConvertDataFormatOnRead@CBinaryRuleReader@@UEAAJW4DataFormats@@PEAUtagPROPVARIANT@@@Z`
- size: `252`
- prototype: `__int64 __fastcall(__int64, int, struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000f510`
- `0x1800129d8`
- `0x18001742c`
- `0x180017490`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18000f59e`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18000f5c9`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18000f59e`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18000f5c9`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000f578`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000f578`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CBinaryRuleReader::ConvertDataFormatOnRead(__int64 a1, int a2, struct tagPROPVARIANT *a3)
{
  unsigned int v4; // ebx
  HRESULT v6; // eax
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
0x18000f510  mov     [rsp-8+arg_0], rbx
0x18000f515  mov     [rsp-8+arg_8], rdi
0x18000f51a  push    rbp
0x18000f51b  mov     rbp, rsp
0x18000f51e  sub     rsp, 40h
0x18000f522  mov     rdi, r8
0x18000f525  xor     ebx, ebx
0x18000f527  cmp     edx, 0Bh
0x18000f52a  jz      short loc_18000F543
0x18000f52c  cmp     edx, 11h
0x18000f52f  jz      short loc_18000F58A
0x18000f531  mov     eax, ebx
0x18000f533  mov     rbx, [rsp+40h+arg_0]
0x18000f538  mov     rdi, [rsp+40h+arg_8]
0x18000f53d  add     rsp, 40h
0x18000f541  pop     rbp
0x18000f542  retn
0x18000f543  cmp     word ptr [r8], 41h ; 'A'
0x18000f548  jz      short loc_18000F5B5
0x18000f54a  mov     eax, 1011h
0x18000f54f  cmp     [r8], ax
0x18000f553  jz      short loc_18000F531
0x18000f555  mov     ebx, 88982F8Eh
0x18000f55a  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18000f561  jz      short loc_18000F531
0x18000f563  mov     ecx, ebx; int
0x18000f565  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18000f56a  jmp     short loc_18000F531
0x18000f56c  mov     ecx, eax; int
0x18000f56e  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18000f573  nop
0x18000f574  lea     rcx, [rbp+pvar]; pvar
0x18000f578  call    cs:__imp_PropVariantClear
0x18000f57e  jmp     short loc_18000F531
0x18000f580  mov     ecx, eax; int
0x18000f582  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18000f587  nop
0x18000f588  jmp     short loc_18000F574
0x18000f58a  xorps   xmm0, xmm0
0x18000f58d  xor     eax, eax
0x18000f58f  movups  xmmword ptr [rbp+pvar], xmm0
0x18000f593  mov     qword ptr [rbp+pvar+10h], rax
0x18000f597  mov     rdx, rdi; pvarSrc
0x18000f59a  lea     rcx, [rbp+pvar]; pvarDest
0x18000f59e  call    cs:__imp_PropVariantCopy
0x18000f5a4  mov     ebx, eax
0x18000f5a6  test    eax, eax
0x18000f5a8  jns     short loc_18000F5E0
0x18000f5aa  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18000f5b1  jnz     short loc_18000F580
0x18000f5b3  jmp     short loc_18000F588
0x18000f5b5  xorps   xmm0, xmm0
0x18000f5b8  xor     eax, eax
0x18000f5ba  movups  xmmword ptr [rbp+pvar], xmm0
0x18000f5be  mov     qword ptr [rbp+pvar+10h], rax
0x18000f5c2  mov     rdx, rdi; pvarSrc
0x18000f5c5  lea     rcx, [rbp+pvar]; pvarDest
0x18000f5c9  call    cs:__imp_PropVariantCopy
0x18000f5cf  mov     ebx, eax
0x18000f5d1  test    eax, eax
0x18000f5d3  jns     short loc_18000F5F4
0x18000f5d5  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18000f5dc  jnz     short loc_18000F56C
0x18000f5de  jmp     short loc_18000F574
0x18000f5e0  mov     rdx, rdi; struct tagPROPVARIANT *
0x18000f5e3  lea     rcx, [rbp+pvar]; struct tagPROPVARIANT *
0x18000f5e7  call    ?ConvertXMPGPSVersionToBuffer@CBinaryRuleReader@@CAJPEAUtagPROPVARIANT@@0@Z; CBinaryRuleReader::ConvertXMPGPSVersionToBuffer(tagPROPVARIANT *,tagPROPVARIANT *)
0x18000f5ec  mov     ebx, eax
0x18000f5ee  test    eax, eax
0x18000f5f0  js      short loc_18000F5AA
0x18000f5f2  jmp     short loc_18000F588
0x18000f5f4  mov     rdx, rdi; struct tagPROPVARIANT *
0x18000f5f7  lea     rcx, [rbp+pvar]; struct tagPROPVARIANT *
0x18000f5fb  call    ?ConvertFromBlobToBuffer@CBinaryRuleReader@@CAJPEBUtagPROPVARIANT@@PEAU2@@Z; CBinaryRuleReader::ConvertFromBlobToBuffer(tagPROPVARIANT const *,tagPROPVARIANT *)
0x18000f600  mov     ebx, eax
0x18000f602  test    eax, eax
0x18000f604  js      short loc_18000F5D5
0x18000f606  jmp     loc_18000F574
```
