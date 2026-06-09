# AC3ParserFilter::Parser::Init(CParseReader *)

- ea: `0x18000a870`
- end: `0x18000aa42`
- name: `?Init@Parser@AC3ParserFilter@@UEAAJPEAVCParseReader@@@Z`
- size: `466`
- prototype: `int(AC3ParserFilter::Parser *__hidden this, struct CParseReader *)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops`

## callees

- `0x180001048`
- `0x180001460`
- `0x180001e98`
- `0x1800068e4`
- `0x180006b18`
- `0x180006b54`
- `0x18000a720`
- `0x18000a870`
- `0x18000ae8c`
- `0x18000d148`
- `0x180034010`

## pseudocode

```c
__int64 __fastcall AC3ParserFilter::Parser::Init(AC3ParserFilter::Parser *this, struct CParseReader *a2)
{
  void (__fastcall **v4)(_QWORD, _QWORD); // rax
  CSpltBaseParser *v5; // rcx
  unsigned int inited; // eax
  unsigned int v7; // ebx
  int FirstFrame; // eax
  unsigned int v9; // edi
  unsigned int v11; // [rsp+20h] [rbp-69h] BYREF
  unsigned __int8 *v12; // [rsp+28h] [rbp-61h] BYREF
  struct tWAVEFORMATEX v13; // [rsp+30h] [rbp-59h] BYREF
  struct _AMMediaType v14; // [rsp+50h] [rbp-39h] BYREF

  (**(void (__fastcall ***)(struct CParseReader *, char *))a2)(a2, (char *)this + 120);
  v4 = *(void (__fastcall ***)(_QWORD, _QWORD))a2;
  v12 = 0;
  ((void (__fastcall **)(struct CParseReader *, _QWORD))v4)[1](a2, 0);
  inited = CSpltBaseParser::NewInitBuffer(v5, &v12, 0x1E00u, a2);
  v7 = inited;
  if ( !inited )
    return 2147746346LL;
  v11 = 0;
  FirstFrame = AC3ParserFilter::WaveType::FindFirstFrame(
                 v12,
                 inited,
                 &v11,
                 (unsigned __int16 (*)(const unsigned __int8 *const))AC3ParserFilter::WaveType::BigEndWord);
  if ( !FirstFrame )
    FirstFrame = AC3ParserFilter::WaveType::FindFirstFrame(
                   v12,
                   v7,
                   &v11,
                   (unsigned __int16 (*)(const unsigned __int8 *const))AC3ParserFilter::WaveType::LittleEndWord);
  if ( FirstFrame <= 1 )
  {
    operator delete(v12);
    return 2147746346LL;
  }
  memset_0(&v14, 0, sizeof(v14));
  v14.lSampleSize = 1;
  v14.majortype = MEDIATYPE_Audio;
  v14.bFixedSizeSamples = 1;
  memset(&v13, 0, sizeof(v13));
  if ( (unsigned int)ParseAC3Header(&v12[v11], &v13) )
  {
    v9 = 0;
    v14.subtype = MEDIASUBTYPE_DOLBY_AC3;
    v14.formattype = FORMAT_WaveFormatEx;
    CMediaType::SetFormat((CMediaType *)&v14, (unsigned __int8 *)&v13, 0x12u);
  }
  else
  {
    v9 = -2147220950;
  }
  (***((void (__fastcall ****)(_QWORD, unsigned __int16 near **, char *))this + 1))(
    *((_QWORD *)this + 1),
    &AC3ParserFilter__szOutputName,
    (char *)this + 24);
  (*(void (__fastcall **)(_QWORD, struct _AMMediaType *))(**((_QWORD **)this + 3) + 16LL))(*((_QWORD *)this + 3), &v14);
  CMediaType::operator=((struct _AMMediaType *)((char *)this + 32), &v14);
  if ( !(*(unsigned int (__fastcall **)(struct CParseReader *))(*(_QWORD *)a2 + 24LL))(a2) )
    *((_QWORD *)this + 15) = 0;
  operator delete(v12);
  *((_BYTE *)this + 128) = 0;
  FreeMediaType(&v14);
  return v9;
}

```

## disassembly

```asm
0x18000a870  mov     [rsp-8+arg_10], rbx
0x18000a875  push    rbp
0x18000a876  push    rdi
0x18000a877  push    r12
0x18000a879  push    r14
0x18000a87b  push    r15
0x18000a87d  lea     rbp, [rsp-37h]
0x18000a882  sub     rsp, 0C0h
0x18000a889  mov     rax, cs:__security_cookie
0x18000a890  xor     rax, rsp
0x18000a893  mov     [rbp+57h+var_30], rax
0x18000a897  mov     rax, [rdx]
0x18000a89a  mov     r14, rdx
0x18000a89d  mov     r15, rcx
0x18000a8a0  lea     rdx, [rcx+78h]
0x18000a8a4  mov     rcx, r14
0x18000a8a7  mov     rax, [rax]
0x18000a8aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a8af  mov     rax, [r14]
0x18000a8b2  xor     edx, edx
0x18000a8b4  mov     rcx, r14
0x18000a8b7  mov     [rbp+57h+var_B8], 0
0x18000a8bf  mov     rax, [rax+8]
0x18000a8c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a8c8  mov     r9, r14; struct CParseReader *
0x18000a8cb  lea     rdx, [rbp+57h+var_B8]; unsigned __int8 **
0x18000a8cf  mov     r8d, 1E00h; unsigned int
0x18000a8d5  call    ?NewInitBuffer@CSpltBaseParser@@IEAAIPEAPEAEIPEAVCParseReader@@@Z; CSpltBaseParser::NewInitBuffer(uchar * *,uint,CParseReader *)
0x18000a8da  mov     ebx, eax
0x18000a8dc  test    eax, eax
0x18000a8de  jz      loc_18000AA19
0x18000a8e4  mov     rcx, [rbp+57h+var_B8]; unsigned __int8 *
0x18000a8e8  lea     r9, ?BigEndWord@WaveType@AC3ParserFilter@@CAGQEBE@Z; unsigned __int16 (*)(const unsigned __int8 *const)
0x18000a8ef  lea     r8, [rbp+57h+var_C0]; unsigned int *
0x18000a8f3  mov     [rbp+57h+var_C0], 0
0x18000a8fa  mov     edx, eax; unsigned int
0x18000a8fc  call    ?FindFirstFrame@WaveType@AC3ParserFilter@@CAHQEBEIPEAIP6AG0@Z@Z; AC3ParserFilter::WaveType::FindFirstFrame(uchar const * const,uint,uint *,ushort (*)(uchar const * const))
0x18000a901  test    eax, eax
0x18000a903  jnz     short loc_18000A91B
0x18000a905  mov     rcx, [rbp+57h+var_B8]; unsigned __int8 *
0x18000a909  lea     r9, ?LittleEndWord@WaveType@AC3ParserFilter@@CAGQEBE@Z; unsigned __int16 (*)(const unsigned __int8 *const)
0x18000a910  lea     r8, [rbp+57h+var_C0]; unsigned int *
0x18000a914  mov     edx, ebx; unsigned int
0x18000a916  call    ?FindFirstFrame@WaveType@AC3ParserFilter@@CAHQEBEIPEAIP6AG0@Z@Z; AC3ParserFilter::WaveType::FindFirstFrame(uchar const * const,uint,uint *,ushort (*)(uchar const * const))
0x18000a91b  mov     ebx, 1
0x18000a920  cmp     eax, ebx
0x18000a922  jle     loc_18000AA10
0x18000a928  xor     edx, edx; Val
0x18000a92a  lea     r8d, [rbx+57h]; Size
0x18000a92e  lea     rcx, [rbp+57h+var_90]; void *
0x18000a932  call    memset_0
0x18000a937  movups  xmm0, xmmword ptr cs:MEDIATYPE_Audio.Data1
0x18000a93e  mov     ecx, [rbp+57h+var_C0]
0x18000a941  lea     rdx, [rbp+57h+var_B0]; struct tWAVEFORMATEX *
0x18000a945  add     rcx, [rbp+57h+var_B8]; unsigned __int8 *
0x18000a949  xor     eax, eax
0x18000a94b  xorps   xmm1, xmm1
0x18000a94e  mov     [rbp+57h+var_90.lSampleSize], ebx
0x18000a951  movdqu  xmmword ptr [rbp+57h+var_90.majortype.Data1], xmm0
0x18000a956  mov     [rbp+57h+var_90.bFixedSizeSamples], ebx
0x18000a959  movups  xmmword ptr [rbp+57h+var_B0.wFormatTag], xmm1
0x18000a95d  mov     [rbp+57h+var_B0.cbSize], ax
0x18000a961  call    ?ParseAC3Header@@YAHPEBEPEAUtWAVEFORMATEX@@@Z; ParseAC3Header(uchar const *,tWAVEFORMATEX *)
0x18000a966  test    eax, eax
0x18000a968  jnz     short loc_18000A971
0x18000a96a  mov     edi, 8004022Ah
0x18000a96f  jmp     short loc_18000A99C
0x18000a971  movups  xmm0, xmmword ptr cs:MEDIASUBTYPE_DOLBY_AC3.Data1
0x18000a978  xor     edi, edi
0x18000a97a  lea     rdx, [rbp+57h+var_B0]; unsigned __int8 *
0x18000a97e  movups  xmm1, xmmword ptr cs:FORMAT_WaveFormatEx.Data1
0x18000a985  lea     rcx, [rbp+57h+var_90]; this
0x18000a989  movdqu  xmmword ptr [rbp+57h+var_90.subtype.Data1], xmm0
0x18000a98e  lea     r8d, [rdi+12h]; unsigned int
0x18000a992  movdqu  xmmword ptr [rbp+57h+var_90.formattype.Data1], xmm1
0x18000a997  call    ?SetFormat@CMediaType@@QEAAHPEAEK@Z; CMediaType::SetFormat(uchar *,ulong)
0x18000a99c  mov     rcx, [r15+8]
0x18000a9a0  lea     r8, [r15+18h]
0x18000a9a4  lea     rdx, ?AC3ParserFilter__szOutputName@@3PAGA; "AC3"
0x18000a9ab  mov     rax, [rcx]
0x18000a9ae  mov     rax, [rax]
0x18000a9b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a9b6  mov     rcx, [r15+18h]
0x18000a9ba  lea     rdx, [rbp+57h+var_90]
0x18000a9be  mov     rax, [rcx]
0x18000a9c1  mov     rax, [rax+10h]
0x18000a9c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a9ca  lea     rcx, [r15+20h]; struct _AMMediaType *
0x18000a9ce  lea     rdx, [rbp+57h+var_90]; struct _AMMediaType *
0x18000a9d2  call    ??4CMediaType@@QEAAAEAV0@AEBV0@@Z; CMediaType::operator=(CMediaType const &)
0x18000a9d7  mov     rax, [r14]
0x18000a9da  mov     rcx, r14
0x18000a9dd  mov     rax, [rax+18h]
0x18000a9e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a9e6  test    eax, eax
0x18000a9e8  jnz     short loc_18000A9F2
0x18000a9ea  mov     qword ptr [r15+78h], 0
0x18000a9f2  mov     rcx, [rbp+57h+var_B8]; void *
0x18000a9f6  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000a9fb  lea     rcx, [rbp+57h+var_90]; struct _AMMediaType *
0x18000a9ff  mov     byte ptr [r15+80h], 0
0x18000aa07  call    ?FreeMediaType@@YAXAEAU_AMMediaType@@@Z; FreeMediaType(_AMMediaType &)
0x18000aa0c  mov     eax, edi
0x18000aa0e  jmp     short loc_18000AA1E
0x18000aa10  mov     rcx, [rbp+57h+var_B8]; void *
0x18000aa14  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000aa19  mov     eax, 8004022Ah
0x18000aa1e  mov     rcx, [rbp+57h+var_30]
0x18000aa22  xor     rcx, rsp; StackCookie
0x18000aa25  call    __security_check_cookie
0x18000aa2a  mov     rbx, [rsp+0E0h+arg_10]
0x18000aa32  add     rsp, 0C0h
0x18000aa39  pop     r15
0x18000aa3b  pop     r14
0x18000aa3d  pop     r12
0x18000aa3f  pop     rdi
0x18000aa40  pop     rbp
0x18000aa41  retn
```
