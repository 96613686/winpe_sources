# UnDecorator::getZName(bool,bool)

- ea: `0x18002d254`
- end: `0x18002d550`
- name: `?getZName@UnDecorator@@AEAA?AVDName@@_N0@Z`
- size: `764`
- prototype: ``
- caller_count: `9`
- callee_count: `13`
- tags: ``

## callers

- `0x180028264`
- `0x180029704`
- `0x180029938`
- `0x18002a4e0`
- `0x18002af70`
- `0x18002b438`
- `0x18002baac`
- `0x18002bd64`
- `0x18002cc20`

## callees

- `0x180020450`
- `0x180023d20`
- `0x1800243b0`
- `0x180024474`
- `0x1800249b4`
- `0x180024b10`
- `0x180024b44`
- `0x1800297b0`
- `0x18002b5ac`
- `0x18002bd64`
- `0x18002d254`
- `0x180032370`
- `0x180060110`

## string_xrefs

- `0x18002d306`: `template-parameter-`
- `0x18002d339`: ``template-parameter-`

## pseudocode

```c
__int64 __fastcall UnDecorator::getZName(__int64 a1, __int64 a2, char a3, char a4)
{
  const char **v5; // r14
  _BYTE *v6; // r10
  __int64 v9; // rcx
  __int64 TemplateName; // rax
  const char *v11; // rcx
  void ***v12; // rdi
  int v13; // ebx
  const char *v14; // rax
  const char *v15; // rax
  _BYTE *v16; // rcx
  int v17; // r8d
  const char *v18; // rax
  const char *v19; // r10
  const char *v20; // rax
  _BYTE *v21; // rdx
  int v22; // r8d
  __int64 (__fastcall *v23)(_QWORD); // rbx
  unsigned int v24; // eax
  __int64 v25; // rax
  __int64 v26; // r9
  DName *v27; // rax
  DName *v28; // rax
  __int64 v29; // r8
  DName *v30; // rax
  __int64 v31; // r8
  int *v32; // r14
  void ****MemoryWithBuffer; // rax
  __int64 v34; // rdx
  const char *v36; // [rsp+20h] [rbp-99h] BYREF
  int v37; // [rsp+28h] [rbp-91h]
  __int64 v38; // [rsp+30h] [rbp-89h] BYREF
  struct UnDecorator *v39; // [rsp+38h] [rbp-81h]
  _BYTE v40[24]; // [rsp+48h] [rbp-71h] BYREF
  _BYTE v41[24]; // [rsp+60h] [rbp-59h] BYREF
  _BYTE v42[24]; // [rsp+78h] [rbp-41h] BYREF
  char v43[24]; // [rsp+90h] [rbp-29h] BYREF
  char v44[24]; // [rsp+A8h] [rbp-11h] BYREF
  char String[16]; // [rsp+C0h] [rbp+7h] BYREF

  v5 = (const char **)(a1 + 256);
  v6 = *(_BYTE **)(a1 + 256);
  if ( (unsigned int)((char)*v6 - 48) <= 9 )
  {
    _mm_lfence();
    v9 = *(_QWORD *)(a1 + 200);
    *v5 = v6 + 1;
    Replicator::operator[](v9, a2);
    return a2;
  }
  if ( *v6 == 63 )
  {
    TemplateName = UnDecorator::getTemplateName(a1, v40, 0);
    v11 = *v5;
    v12 = *(void ****)TemplateName;
    v13 = *(_DWORD *)(TemplateName + 16);
    if ( **v5 != 64 )
    {
      v12 = &off_18006AFC0;
      v13 = (*v11 != 0) + 1;
      if ( *v11 )
        v12 = 0;
      goto LABEL_37;
    }
    v14 = v11 + 1;
    goto LABEL_33;
  }
  v15 = "template-parameter-";
  v16 = *(_BYTE **)(a1 + 256);
  v17 = 18;
  do
  {
    if ( !*v16 )
      break;
    if ( *v16 != *v15 )
      break;
    ++v16;
    ++v15;
    --v17;
  }
  while ( v17 );
  if ( *v16 == *v15 )
  {
    v18 = "`template-parameter-";
    v37 = 20;
    v19 = v6 + 19;
  }
  else
  {
    v20 = "generic-type-";
    v21 = v6;
    v22 = 12;
    do
    {
      if ( !*v21 )
        break;
      if ( *v21 != *v20 )
        break;
      ++v21;
      ++v20;
      --v22;
    }
    while ( v22 );
    if ( *v21 != *v20 )
    {
      if ( a4 && *v6 == 64 )
      {
        v12 = 0;
        v14 = v6 + 1;
        v13 = 0;
LABEL_33:
        *v5 = v14;
        goto LABEL_37;
      }
      v27 = DName::DName((DName *)v42, (struct UnDecorator *)a1, v5, 64);
      goto LABEL_35;
    }
    v18 = "`generic-type-";
    v37 = 14;
    v19 = v6 + 13;
  }
  v36 = v18;
  *v5 = v19;
  UnDecorator::getSignedDimension(a1, &v38);
  if ( (*(_DWORD *)(a1 + 272) & 0x4000) != 0 && *(_QWORD *)(a1 + 280) )
  {
    *(_OWORD *)String = 0;
    if ( v38 )
      *(_BYTE *)(*(__int64 (__fastcall **)(__int64, char *, char *))(*(_QWORD *)v38 + 24LL))(v38, String, &String[15]) = 0;
    v23 = *(__int64 (__fastcall **)(_QWORD))(a1 + 280);
    v24 = atol(String);
    v25 = v23(v24);
    if ( v25 )
    {
      LOBYTE(v26) = 0;
      v27 = (DName *)DName::DName(v43, a1, v25, v26);
    }
    else
    {
      v28 = DName::DName((DName *)v41, v39, (const struct StringLiteral *)&v36);
      DName::operator+(v28, v40, &v38);
      LOBYTE(v29) = 39;
      v27 = (DName *)DName::operator+(v40, v44, v29);
    }
    v13 = *((_DWORD *)v27 + 4);
    goto LABEL_36;
  }
  v30 = DName::DName((DName *)v41, v39, (const struct StringLiteral *)&v36);
  DName::operator+(v30, v40, &v38);
  LOBYTE(v31) = 39;
  v27 = (DName *)DName::operator+(v40, v42, v31);
LABEL_35:
  v13 = *((_DWORD *)v27 + 4);
LABEL_36:
  v12 = *(void ****)v27;
LABEL_37:
  if ( a3 )
  {
    v32 = *(int **)(a1 + 200);
    if ( *v32 != 9 )
    {
      if ( v12 )
      {
        MemoryWithBuffer = (void ****)_HeapManager::getMemoryWithBuffer(
                                        (_HeapManager *)(*((_QWORD *)v32 + 11) + 216LL),
                                        0x18u);
        if ( MemoryWithBuffer )
        {
          MemoryWithBuffer[1] = (void ***)a1;
          *MemoryWithBuffer = v12;
          *((_DWORD *)MemoryWithBuffer + 4) = v13;
          v34 = *v32;
          *v32 = v34 + 1;
          *(_QWORD *)&v32[2 * v34 + 4] = MemoryWithBuffer;
        }
      }
    }
  }
  *(_QWORD *)(a2 + 8) = a1;
  *(_QWORD *)a2 = v12;
  *(_DWORD *)(a2 + 16) = v13;
  return a2;
}

```

## disassembly

```asm
0x18002d254  mov     [rsp-8+arg_10], rbx
0x18002d259  push    rbp
0x18002d25a  push    rsi
0x18002d25b  push    rdi
0x18002d25c  push    r12
0x18002d25e  push    r13
0x18002d260  push    r14
0x18002d262  push    r15
0x18002d264  lea     rbp, [rsp-27h]
0x18002d269  sub     rsp, 0E0h
0x18002d270  mov     rax, cs:__security_cookie
0x18002d277  xor     rax, rsp
0x18002d27a  mov     [rbp+57h+var_40], rax
0x18002d27e  mov     r12b, r8b
0x18002d281  lea     r14, [rcx+100h]
0x18002d288  mov     r10, [r14]
0x18002d28b  mov     r15, rdx
0x18002d28e  mov     rsi, rcx
0x18002d291  movsx   r8d, byte ptr [r10]
0x18002d295  add     r8d, 0FFFFFFD0h
0x18002d299  cmp     r8d, 9
0x18002d29d  ja      short loc_18002D2BD
0x18002d29f  lfence
0x18002d2a2  mov     rcx, [rcx+0C8h]
0x18002d2a9  lea     rdx, [r10+1]
0x18002d2ad  mov     [r14], rdx
0x18002d2b0  mov     rdx, r15
0x18002d2b3  call    ??AReplicator@@QEBA?AVDName@@H@Z; Replicator::operator[](int)
0x18002d2b8  jmp     loc_18002D526
0x18002d2bd  xor     r13d, r13d
0x18002d2c0  cmp     byte ptr [r10], 3Fh ; '?'
0x18002d2c4  jnz     short loc_18002D306
0x18002d2c6  xor     r8d, r8d
0x18002d2c9  lea     rdx, [rbp+57h+var_C8]
0x18002d2cd  call    ?getTemplateName@UnDecorator@@AEAA?AVDName@@_N@Z; UnDecorator::getTemplateName(bool)
0x18002d2d2  mov     rcx, [r14]
0x18002d2d5  mov     rdi, [rax]
0x18002d2d8  cmp     byte ptr [rcx], 40h ; '@'
0x18002d2db  mov     ebx, [rax+10h]
0x18002d2de  jnz     short loc_18002D2E9
0x18002d2e0  lea     rax, [rcx+1]
0x18002d2e4  jmp     loc_18002D4B5
0x18002d2e9  mov     al, [rcx]
0x18002d2eb  lea     rdi, off_18006AFC0
0x18002d2f2  neg     al
0x18002d2f4  sbb     ebx, ebx
0x18002d2f6  neg     ebx
0x18002d2f8  inc     ebx
0x18002d2fa  cmp     [rcx], r13b
0x18002d2fd  cmovnz  rdi, r13
0x18002d301  jmp     loc_18002D4D2
0x18002d306  lea     rax, aTemplateParame_0; "template-parameter-"
0x18002d30d  mov     rcx, r10
0x18002d310  mov     r8d, 12h
0x18002d316  or      r11d, 0FFFFFFFFh
0x18002d31a  mov     dl, [rcx]
0x18002d31c  test    dl, dl
0x18002d31e  jz      short loc_18002D32F
0x18002d320  cmp     dl, [rax]
0x18002d322  jnz     short loc_18002D32F
0x18002d324  inc     rcx
0x18002d327  inc     rax
0x18002d32a  add     r8d, r11d
0x18002d32d  jnz     short loc_18002D31A
0x18002d32f  movzx   ecx, byte ptr [rcx]
0x18002d332  movzx   eax, byte ptr [rax]
0x18002d335  cmp     ecx, eax
0x18002d337  jnz     short loc_18002D34E
0x18002d339  lea     rax, aTemplateParame_1; "`template-parameter-"
0x18002d340  mov     dword ptr [rsp+110h+var_F0+8], 14h
0x18002d348  add     r10, 13h
0x18002d34c  jmp     short loc_18002D394
0x18002d34e  lea     rax, aGenericType_0; "generic-type-"
0x18002d355  mov     rdx, r10
0x18002d358  mov     r8d, 0Ch
0x18002d35e  mov     cl, [rdx]
0x18002d360  test    cl, cl
0x18002d362  jz      short loc_18002D373
0x18002d364  cmp     cl, [rax]
0x18002d366  jnz     short loc_18002D373
0x18002d368  inc     rdx
0x18002d36b  inc     rax
0x18002d36e  add     r8d, r11d
0x18002d371  jnz     short loc_18002D35E
0x18002d373  movzx   ecx, byte ptr [rax]
0x18002d376  movzx   eax, byte ptr [rdx]
0x18002d379  cmp     eax, ecx
0x18002d37b  jnz     loc_18002D4A0
0x18002d381  lea     rax, aGenericType; "`generic-type-"
0x18002d388  mov     dword ptr [rsp+110h+var_F0+8], 0Eh
0x18002d390  add     r10, 0Dh
0x18002d394  mov     qword ptr [rsp+110h+var_F0], rax
0x18002d399  lea     rdx, [rsp+110h+var_E0]
0x18002d39e  movaps  xmm0, [rsp+110h+var_F0]
0x18002d3a3  mov     rcx, rsi
0x18002d3a6  movdqa  [rsp+110h+var_F0], xmm0
0x18002d3ac  mov     [r14], r10
0x18002d3af  call    ?getSignedDimension@UnDecorator@@AEAA?AVDName@@XZ; UnDecorator::getSignedDimension(void)
0x18002d3b4  test    dword ptr [rsi+110h], 4000h
0x18002d3be  jz      loc_18002D46A
0x18002d3c4  cmp     [rsi+118h], r13
0x18002d3cb  jz      loc_18002D46A
0x18002d3d1  mov     rcx, [rsp+110h+var_E0]
0x18002d3d6  xorps   xmm0, xmm0
0x18002d3d9  movups  xmmword ptr [rbp+57h+String], xmm0
0x18002d3dd  test    rcx, rcx
0x18002d3e0  jz      short loc_18002D3FA
0x18002d3e2  mov     rax, [rcx]
0x18002d3e5  lea     r8, [rbp+57h+String+0Fh]
0x18002d3e9  lea     rdx, [rbp+57h+String]
0x18002d3ed  mov     rax, [rax+18h]
0x18002d3f1  call    cs:__guard_dispatch_icall_fptr
0x18002d3f7  mov     [rax], r13b
0x18002d3fa  mov     rbx, [rsi+118h]
0x18002d401  lea     rcx, [rbp+57h+String]; String
0x18002d405  call    atol
0x18002d40a  mov     ecx, eax
0x18002d40c  mov     rax, rbx
0x18002d40f  call    cs:__guard_dispatch_icall_fptr
0x18002d415  test    rax, rax
0x18002d418  jz      short loc_18002D42E
0x18002d41a  mov     r9b, r13b
0x18002d41d  lea     rcx, [rbp+57h+var_80]
0x18002d421  mov     r8, rax
0x18002d424  mov     rdx, rsi
0x18002d427  call    ??$?0$0A@@DName@@QEAA@PEAVUnDecorator@@PEBDU?$StringLifeSelector@$0A@@@@Z; DName::DName(UnDecorator *,char const *,StringLifeSelector<0>)
0x18002d42c  jmp     short loc_18002D462
0x18002d42e  mov     rdx, [rsp+110h+var_D8]; struct UnDecorator *
0x18002d433  lea     r8, [rsp+110h+var_F0]; struct StringLiteral *
0x18002d438  lea     rcx, [rbp+57h+var_B0]; this
0x18002d43c  call    ??0DName@@QEAA@PEAVUnDecorator@@AEBUStringLiteral@@@Z; DName::DName(UnDecorator *,StringLiteral const &)
0x18002d441  lea     r8, [rsp+110h+var_E0]
0x18002d446  mov     rcx, rax
0x18002d449  lea     rdx, [rbp+57h+var_C8]
0x18002d44d  call    ??HDName@@QEBA?AV0@AEBV0@@Z; DName::operator+(DName const &)
0x18002d452  mov     r8b, 27h ; '''
0x18002d455  lea     rdx, [rbp+57h+var_68]
0x18002d459  lea     rcx, [rbp+57h+var_C8]
0x18002d45d  call    ??HDName@@QEBA?AV0@D@Z; DName::operator+(char)
0x18002d462  mov     rbx, rax
0x18002d465  mov     ebx, [rax+10h]
0x18002d468  jmp     short loc_18002D4CF
0x18002d46a  mov     rdx, [rsp+110h+var_D8]; struct UnDecorator *
0x18002d46f  lea     r8, [rsp+110h+var_F0]; struct StringLiteral *
0x18002d474  lea     rcx, [rbp+57h+var_B0]; this
0x18002d478  call    ??0DName@@QEAA@PEAVUnDecorator@@AEBUStringLiteral@@@Z; DName::DName(UnDecorator *,StringLiteral const &)
0x18002d47d  lea     r8, [rsp+110h+var_E0]
0x18002d482  mov     rcx, rax
0x18002d485  lea     rdx, [rbp+57h+var_C8]
0x18002d489  call    ??HDName@@QEBA?AV0@AEBV0@@Z; DName::operator+(DName const &)
0x18002d48e  mov     r8b, 27h ; '''
0x18002d491  lea     rdx, [rbp+57h+var_98]
0x18002d495  lea     rcx, [rbp+57h+var_C8]
0x18002d499  call    ??HDName@@QEBA?AV0@D@Z; DName::operator+(char)
0x18002d49e  jmp     short loc_18002D4CC
0x18002d4a0  test    r9b, r9b
0x18002d4a3  jz      short loc_18002D4BA
0x18002d4a5  cmp     byte ptr [r10], 40h ; '@'
0x18002d4a9  jnz     short loc_18002D4BA
0x18002d4ab  mov     rdi, r13
0x18002d4ae  lea     rax, [r10+1]
0x18002d4b2  mov     ebx, r13d
0x18002d4b5  mov     [r14], rax
0x18002d4b8  jmp     short loc_18002D4D2
0x18002d4ba  mov     r9b, 40h ; '@'; char
0x18002d4bd  lea     rcx, [rbp+57h+var_98]; this
0x18002d4c1  mov     r8, r14; char **
0x18002d4c4  mov     rdx, rsi; struct UnDecorator *
0x18002d4c7  call    ??0DName@@QEAA@PEAVUnDecorator@@AEAPEBDD@Z; DName::DName(UnDecorator *,char const * &,char)
0x18002d4cc  mov     ebx, [rax+10h]
0x18002d4cf  mov     rdi, [rax]
0x18002d4d2  test    r12b, r12b
0x18002d4d5  jz      short loc_18002D51B
0x18002d4d7  mov     r14, [rsi+0C8h]
0x18002d4de  cmp     dword ptr [r14], 9
0x18002d4e2  jz      short loc_18002D51B
0x18002d4e4  test    rdi, rdi
0x18002d4e7  jz      short loc_18002D51B
0x18002d4e9  mov     rcx, [r14+58h]
0x18002d4ed  mov     edx, 18h; unsigned __int64
0x18002d4f2  add     rcx, 0D8h; this
0x18002d4f9  call    ?getMemoryWithBuffer@_HeapManager@@QEAAPEAX_K@Z; _HeapManager::getMemoryWithBuffer(unsigned __int64)
0x18002d4fe  test    rax, rax
0x18002d501  jz      short loc_18002D51B
0x18002d503  mov     [rax+8], rsi
0x18002d507  mov     [rax], rdi
0x18002d50a  mov     [rax+10h], ebx
0x18002d50d  movsxd  rdx, dword ptr [r14]
0x18002d510  lea     ecx, [rdx+1]
0x18002d513  mov     [r14], ecx
0x18002d516  mov     [r14+rdx*8+10h], rax
0x18002d51b  mov     [r15+8], rsi
0x18002d51f  mov     [r15], rdi
0x18002d522  mov     [r15+10h], ebx
0x18002d526  mov     rax, r15
0x18002d529  mov     rcx, [rbp+57h+var_40]
0x18002d52d  xor     rcx, rsp; StackCookie
0x18002d530  call    __security_check_cookie
0x18002d535  mov     rbx, [rsp+110h+arg_10]
0x18002d53d  add     rsp, 0E0h
0x18002d544  pop     r15
0x18002d546  pop     r14
0x18002d548  pop     r13
0x18002d54a  pop     r12
0x18002d54c  pop     rdi
0x18002d54d  pop     rsi
0x18002d54e  pop     rbp
0x18002d54f  retn
```
