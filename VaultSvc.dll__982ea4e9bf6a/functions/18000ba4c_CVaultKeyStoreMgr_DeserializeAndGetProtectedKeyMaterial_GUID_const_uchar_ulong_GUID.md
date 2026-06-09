# CVaultKeyStoreMgr::DeserializeAndGetProtectedKeyMaterial(_GUID const *,uchar * *,ulong *,_GUID *)

- ea: `0x18000ba4c`
- end: `0x18000bc8e`
- name: `?DeserializeAndGetProtectedKeyMaterial@CVaultKeyStoreMgr@@QEAAKPEBU_GUID@@PEAPEAEPEAKPEAU2@@Z`
- size: `578`
- prototype: `__int64 __fastcall(CVaultKeyStoreMgr *this, struct _GUID *, unsigned __int8 **, unsigned int *, struct _GUID *)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, registry_config`

## callers

- `0x18000af40`
- `0x18003d084`

## callees

- `0x180003140`
- `0x18000a6f4`
- `0x18000ae60`
- `0x18000ba4c`
- `0x18004b430`
- `0x18004d010`

## pseudocode

```c
__int64 __fastcall CVaultKeyStoreMgr::DeserializeAndGetProtectedKeyMaterial(
        CVaultKeyStoreMgr *this,
        struct _GUID *a2,
        unsigned __int8 **a3,
        unsigned int *a4,
        struct _GUID *a5)
{
  __int64 v8; // rdi
  unsigned int v9; // ebx
  unsigned __int8 *v10; // r14
  unsigned int v11; // ebx
  struct _GUID *v12; // r12
  unsigned int v13; // ebx
  __int64 v14; // rsi
  unsigned __int8 *v15; // r15
  unsigned int v17; // [rsp+20h] [rbp-51h] BYREF
  __int64 v18; // [rsp+28h] [rbp-49h] BYREF
  char v19; // [rsp+30h] [rbp-41h]
  __int64 v20; // [rsp+38h] [rbp-39h] BYREF
  _OWORD *v21; // [rsp+40h] [rbp-31h] BYREF
  int v22; // [rsp+48h] [rbp-29h]
  unsigned int *v23; // [rsp+50h] [rbp-21h]
  __int128 v24; // [rsp+58h] [rbp-19h] BYREF
  __int128 v25; // [rsp+68h] [rbp-9h]
  _OWORD Buf2[4]; // [rsp+78h] [rbp+7h] BYREF

  v23 = a4;
  v21 = 0;
  v22 = 0;
  v20 = 0;
  v17 = 0;
  v8 = *(_QWORD *)this;
  v18 = v8;
  if ( v8 )
  {
    (**(void (__fastcall ***)(__int64))v8)(v8);
    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v8 + 200LL))(v8, 0);
  }
  v19 = 1;
  v9 = (*(__int64 (__fastcall **)(_QWORD, _OWORD **, unsigned int *))(**(_QWORD **)this + 56LL))(
         *(_QWORD *)this,
         &v21,
         &v17);
  if ( v9 )
  {
    CVaultStoreLock::~CVaultStoreLock((CVaultStoreLock *)&v18);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete((__int64)&v20);
    return v9;
  }
  else if ( v17 < 0x10 )
  {
LABEL_25:
    CVaultStoreLock::~CVaultStoreLock((CVaultStoreLock *)&v18);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete((__int64)&v20);
    return 122;
  }
  else
  {
    v24 = *v21;
    v10 = (unsigned __int8 *)(v21 + 1);
    v11 = v17 - 16;
    v17 -= 16;
    v12 = (struct _GUID *)&v24;
    if ( a2 )
      v12 = a2;
    if ( a5 )
      *a5 = *v12;
    while ( 1 )
    {
      if ( v11 < 0x10 )
      {
        if ( v8 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 208LL))(v8);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 8LL))(v8);
        }
        CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete((__int64)&v20);
        return 122;
      }
      Buf2[0] = *(_OWORD *)v10;
      v13 = v11 - 16;
      v17 = v13;
      v25 = 0;
      if ( v13 < 4 )
        goto LABEL_25;
      v14 = *((unsigned int *)v10 + 4);
      v11 = v13 - 4;
      v17 = v11;
      if ( (unsigned int)v14 > v11 )
        goto LABEL_25;
      v15 = v10 + 20;
      if ( (_DWORD)v14 )
      {
        v10 = &v15[v14];
        v11 -= v14;
        v17 = v11;
      }
      else
      {
        v10 += 20;
        v15 = (unsigned __int8 *)*((_QWORD *)&v25 + 1);
      }
      if ( !memcmp_0(v12, Buf2, 0x10u) )
        break;
      if ( !v11 )
      {
        CVaultStoreLock::~CVaultStoreLock((CVaultStoreLock *)&v18);
        CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete((__int64)&v20);
        return 1168;
      }
    }
    if ( a3 )
    {
      *v23 = v14;
      v9 = DuplicateBuffer(v15, (unsigned int)v14, a3);
      CVaultStoreLock::~CVaultStoreLock((CVaultStoreLock *)&v18);
      CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete((__int64)&v20);
      return v9;
    }
    CVaultStoreLock::~CVaultStoreLock((CVaultStoreLock *)&v18);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete((__int64)&v20);
    return 0;
  }
}

```

## disassembly

```asm
0x18000ba4c  mov     [rsp-8+arg_8], rbx
0x18000ba51  push    rbp
0x18000ba52  push    rsi
0x18000ba53  push    rdi
0x18000ba54  push    r12
0x18000ba56  push    r13
0x18000ba58  push    r14
0x18000ba5a  push    r15
0x18000ba5c  lea     rbp, [rsp-1Fh]
0x18000ba61  sub     rsp, 90h
0x18000ba68  mov     [rbp+4Fh+var_70], r9
0x18000ba6c  mov     r13, r8
0x18000ba6f  mov     r15, rdx
0x18000ba72  mov     rbx, rcx
0x18000ba75  mov     rsi, [rbp+4Fh+arg_20]
0x18000ba79  xor     r14d, r14d
0x18000ba7c  mov     [rbp+4Fh+var_80], r14
0x18000ba80  mov     [rbp+4Fh+var_78], r14d
0x18000ba84  mov     [rbp+4Fh+var_88], r14
0x18000ba88  mov     [rbp+4Fh+var_A0], r14d
0x18000ba8c  mov     rdi, [rcx]
0x18000ba8f  mov     [rbp+4Fh+var_98], rdi
0x18000ba93  test    rdi, rdi
0x18000ba96  jz      short loc_18000BABA
0x18000ba98  mov     rax, [rdi]
0x18000ba9b  mov     rcx, rdi
0x18000ba9e  mov     rax, [rax]
0x18000baa1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000baa6  mov     rax, [rdi]
0x18000baa9  xor     edx, edx
0x18000baab  mov     rcx, rdi
0x18000baae  mov     rax, [rax+0C8h]
0x18000bab5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000baba  mov     [rbp+4Fh+var_90], 1
0x18000babe  mov     rcx, [rbx]
0x18000bac1  mov     rax, [rcx]
0x18000bac4  lea     r8, [rbp+4Fh+var_A0]
0x18000bac8  lea     rdx, [rbp+4Fh+var_80]
0x18000bacc  mov     rax, [rax+38h]
0x18000bad0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bad5  mov     ebx, eax
0x18000bad7  test    eax, eax
0x18000bad9  jnz     loc_18000BC25
0x18000badf  mov     ebx, [rbp+4Fh+var_A0]
0x18000bae2  cmp     ebx, 10h
0x18000bae5  jb      loc_18000BC3B
0x18000baeb  mov     rax, [rbp+4Fh+var_80]
0x18000baef  movups  xmm0, xmmword ptr [rax]
0x18000baf2  movdqu  [rbp+4Fh+var_68], xmm0
0x18000baf7  lea     r14, [rax+10h]
0x18000bafb  add     ebx, 0FFFFFFF0h
0x18000bafe  mov     [rbp+4Fh+var_A0], ebx
0x18000bb01  lea     r12, [rbp+4Fh+var_68]
0x18000bb05  test    r15, r15
0x18000bb08  cmovnz  r12, r15
0x18000bb0c  test    rsi, rsi
0x18000bb0f  jz      short loc_18000BB1A
0x18000bb11  movups  xmm0, xmmword ptr [r12]
0x18000bb16  movdqu  xmmword ptr [rsi], xmm0
0x18000bb1a  cmp     ebx, 10h
0x18000bb1d  jb      loc_18000BBD4
0x18000bb23  movups  xmm0, xmmword ptr [r14]
0x18000bb27  movdqu  [rbp+4Fh+Buf2], xmm0
0x18000bb2c  add     ebx, 0FFFFFFF0h
0x18000bb2f  mov     [rbp+4Fh+var_A0], ebx
0x18000bb32  xorps   xmm0, xmm0
0x18000bb35  movups  [rbp+4Fh+var_58], xmm0
0x18000bb39  cmp     ebx, 4
0x18000bb3c  jb      loc_18000BC75
0x18000bb42  mov     esi, [r14+10h]
0x18000bb46  add     ebx, 0FFFFFFFCh
0x18000bb49  mov     [rbp+4Fh+var_A0], ebx
0x18000bb4c  cmp     esi, ebx
0x18000bb4e  ja      loc_18000BC75
0x18000bb54  lea     r15, [r14+14h]
0x18000bb58  test    esi, esi
0x18000bb5a  jz      loc_18000BC51
0x18000bb60  lea     r14, [r15+rsi]
0x18000bb64  sub     ebx, esi
0x18000bb66  mov     [rbp+4Fh+var_A0], ebx
0x18000bb69  mov     r8d, 10h; Size
0x18000bb6f  lea     rdx, [rbp+4Fh+Buf2]; Buf2
0x18000bb73  mov     rcx, r12; Buf1
0x18000bb76  call    memcmp_0
0x18000bb7b  test    eax, eax
0x18000bb7d  jz      short loc_18000BB9E
0x18000bb7f  test    ebx, ebx
0x18000bb81  jnz     short loc_18000BB1A
0x18000bb83  lea     rcx, [rbp+4Fh+var_98]; this
0x18000bb87  call    ??1CVaultStoreLock@@QEAA@XZ; CVaultStoreLock::~CVaultStoreLock(void)
0x18000bb8c  nop
0x18000bb8d  lea     rcx, [rbp+4Fh+var_88]
0x18000bb91  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18000bb96  nop
0x18000bb97  mov     eax, 490h
0x18000bb9c  jmp     short loc_18000BC0A
0x18000bb9e  test    r13, r13
0x18000bba1  jz      loc_18000BC5D
0x18000bba7  mov     rax, [rbp+4Fh+var_70]
0x18000bbab  mov     [rax], esi
0x18000bbad  mov     r8, r13; unsigned __int8 **
0x18000bbb0  mov     edx, esi; Size
0x18000bbb2  mov     rcx, r15; Src
0x18000bbb5  call    ?DuplicateBuffer@@YAKPEAEKPEAPEAE@Z; DuplicateBuffer(uchar *,ulong,uchar * *)
0x18000bbba  mov     ebx, eax
0x18000bbbc  lea     rcx, [rbp+4Fh+var_98]; this
0x18000bbc0  call    ??1CVaultStoreLock@@QEAA@XZ; CVaultStoreLock::~CVaultStoreLock(void)
0x18000bbc5  nop
0x18000bbc6  lea     rcx, [rbp+4Fh+var_88]
0x18000bbca  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18000bbcf  nop
0x18000bbd0  mov     eax, ebx
0x18000bbd2  jmp     short loc_18000BC0A
0x18000bbd4  test    rdi, rdi
0x18000bbd7  jz      short loc_18000BBFB
0x18000bbd9  mov     rax, [rdi]
0x18000bbdc  mov     rcx, rdi
0x18000bbdf  mov     rax, [rax+0D0h]
0x18000bbe6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bbeb  mov     rax, [rdi]
0x18000bbee  mov     rcx, rdi
0x18000bbf1  mov     rax, [rax+8]
0x18000bbf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bbfa  nop
0x18000bbfb  lea     rcx, [rbp+4Fh+var_88]
0x18000bbff  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18000bc04  nop
0x18000bc05  mov     eax, 7Ah ; 'z'
0x18000bc0a  mov     rbx, [rsp+0C0h+arg_8]
0x18000bc12  add     rsp, 90h
0x18000bc19  pop     r15
0x18000bc1b  pop     r14
0x18000bc1d  pop     r13
0x18000bc1f  pop     r12
0x18000bc21  pop     rdi
0x18000bc22  pop     rsi
0x18000bc23  pop     rbp
0x18000bc24  retn
0x18000bc25  lea     rcx, [rbp+4Fh+var_98]; this
0x18000bc29  call    ??1CVaultStoreLock@@QEAA@XZ; CVaultStoreLock::~CVaultStoreLock(void)
0x18000bc2e  nop
0x18000bc2f  lea     rcx, [rbp+4Fh+var_88]
0x18000bc33  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18000bc38  nop
0x18000bc39  jmp     short loc_18000BBD0
0x18000bc3b  lea     rcx, [rbp+4Fh+var_98]; this
0x18000bc3f  call    ??1CVaultStoreLock@@QEAA@XZ; CVaultStoreLock::~CVaultStoreLock(void)
0x18000bc44  nop
0x18000bc45  lea     rcx, [rbp+4Fh+var_88]
0x18000bc49  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18000bc4e  nop
0x18000bc4f  jmp     short loc_18000BC05
0x18000bc51  mov     r14, r15
0x18000bc54  mov     r15, qword ptr [rbp+4Fh+var_58+8]
0x18000bc58  jmp     loc_18000BB69
0x18000bc5d  lea     rcx, [rbp+4Fh+var_98]; this
0x18000bc61  call    ??1CVaultStoreLock@@QEAA@XZ; CVaultStoreLock::~CVaultStoreLock(void)
0x18000bc66  nop
0x18000bc67  lea     rcx, [rbp+4Fh+var_88]
0x18000bc6b  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18000bc70  nop
0x18000bc71  xor     eax, eax
0x18000bc73  jmp     short loc_18000BC0A
0x18000bc75  lea     rcx, [rbp+4Fh+var_98]; this
0x18000bc79  call    ??1CVaultStoreLock@@QEAA@XZ; CVaultStoreLock::~CVaultStoreLock(void)
0x18000bc7e  nop
0x18000bc7f  lea     rcx, [rbp+4Fh+var_88]
0x18000bc83  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18000bc88  nop
0x18000bc89  jmp     loc_18000BC05
```
