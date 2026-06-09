# CFormatConverterNChannel::ColorTransformOverride(IWICColorContext *,IWICColorContext *,int *)

- ea: `0x18001d240`
- end: `0x18001d4f5`
- name: `?ColorTransformOverride@CFormatConverterNChannel@@UEAAJPEAUIWICColorContext@@0PEAH@Z`
- size: `693`
- prototype: `int(CFormatConverterNChannel *__hidden this, struct IWICColorContext *, struct IWICColorContext *, int *)`
- caller_count: `0`
- callee_count: `10`
- tags: ``

## callees

- `0x18000be7c`
- `0x180011760`
- `0x18001179c`
- `0x180013ab8`
- `0x1800171c4`
- `0x18001d240`
- `0x18001d4fc`
- `0x180021a30`
- `0x180022348`
- `0x180033010`

## pseudocode

```c
__int64 __fastcall CFormatConverterNChannel::ColorTransformOverride(
        CFormatConverterNChannel *this,
        struct IWICColorContext *a2,
        struct IWICColorContext *a3,
        int *a4)
{
  __int64 v7; // rdi
  void *v8; // r14
  unsigned int v10; // ebx
  int ProfileHandle; // eax
  void *v12; // r15
  int v13; // eax
  int v15; // ecx
  int v16; // eax
  __int64 v17; // rcx
  __int64 v18; // rcx
  void *v19; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v20; // [rsp+28h] [rbp-D8h] BYREF
  void *v21; // [rsp+30h] [rbp-D0h] BYREF
  struct tagPROFILEHEADER v22; // [rsp+40h] [rbp-C0h] BYREF
  struct tagPROFILEHEADER v23; // [rsp+C0h] [rbp-40h] BYREF

  v7 = 0;
  v20 = 0;
  v8 = 0;
  v21 = 0;
  v19 = 0;
  memset_0(&v22, 0, sizeof(v22));
  memset_0(&v23, 0, sizeof(v23));
  if ( a2 && a3 && a4 )
  {
    *a4 = 0;
    v10 = 0;
    if ( *((_DWORD *)this + 14) == 15 )
      return v10;
    ProfileHandle = CIcmColorTransform::GetProfileHandle(a2, &v21);
    v12 = v21;
    v10 = ProfileHandle;
    if ( ProfileHandle < 0 )
      goto LABEL_8;
    v13 = CIcmColorTransform::GetProfileHandle(a3, &v19);
    v10 = v13;
    if ( v13 < 0 )
    {
      if ( g_doStackCaptures )
        DoStackCapture(v13);
      v8 = v19;
      goto LABEL_14;
    }
    ICMModule::GetColorProfileHeader(v12, &v22);
    v8 = v19;
    ICMModule::GetColorProfileHeader(v19, &v23);
    if ( v22.phDataColorSpace != 860048466 )
    {
      switch ( v22.phDataColorSpace )
      {
        case 0x34434C52u:
          goto LABEL_35;
        case 0x35434C52u:
          v15 = 5;
          goto LABEL_37;
        case 0x36434C52u:
          v15 = 6;
          goto LABEL_37;
        case 0x37434C52u:
          v15 = 7;
          goto LABEL_37;
        case 0x38434C52u:
          v15 = 8;
          goto LABEL_37;
        case 0x434D594Bu:
LABEL_35:
          v15 = 4;
          goto LABEL_37;
      }
      if ( v22.phDataColorSpace != 1380401696 )
      {
        v15 = 0;
LABEL_37:
        if ( v15 != *((_DWORD *)this + 17) - *((_DWORD *)this + 19) || v23.phDataColorSpace != 1380401696 )
          goto LABEL_14;
        LODWORD(v19) = 0;
        v16 = WICCreateIcmColorTransform(&v20);
        v10 = v16;
        if ( v16 < 0 )
        {
          if ( g_doStackCaptures )
            DoStackCapture(v16);
          v7 = v20;
          goto LABEL_14;
        }
        v7 = v20;
        ProfileHandle = (*(__int64 (__fastcall **)(__int64, void *, void *))(*(_QWORD *)v20 + 72LL))(v20, v12, v8);
        v10 = ProfileHandle;
        if ( ProfileHandle >= 0 )
        {
          v17 = *((_QWORD *)this + 17);
          if ( v17 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
          v18 = *((unsigned int *)this + 14);
          *((_QWORD *)this + 17) = v7;
          v7 = 0;
          ProfileHandle = HrNChanPfToTableIndex(v18, &v19);
          v10 = ProfileHandle;
          if ( ProfileHandle >= 0 )
          {
            *((_DWORD *)this + 16) = *((_DWORD *)qword_180037D70 + (unsigned int)v19);
            *((_DWORD *)this + 36) = 1;
            *a4 = 1;
            goto LABEL_14;
          }
          if ( !g_doStackCaptures )
            goto LABEL_14;
          goto LABEL_9;
        }
LABEL_8:
        if ( !g_doStackCaptures )
        {
LABEL_14:
          if ( v12 )
            ICMModule::CloseColorProfile(v12);
          if ( v8 )
            ICMModule::CloseColorProfile(v8);
          if ( v7 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
          return v10;
        }
LABEL_9:
        DoStackCapture(ProfileHandle);
        goto LABEL_14;
      }
    }
    v15 = 3;
    goto LABEL_37;
  }
  v10 = -2147024809;
  if ( g_doStackCaptures )
    DoStackCapture(-2147024809);
  return v10;
}

```

## disassembly

```asm
0x18001d240  push    rbp
0x18001d242  push    rbx
0x18001d243  push    rsi
0x18001d244  push    rdi
0x18001d245  push    r12
0x18001d247  push    r13
0x18001d249  push    r14
0x18001d24b  push    r15
0x18001d24d  lea     rbp, [rsp-58h]
0x18001d252  sub     rsp, 158h
0x18001d259  mov     rax, cs:__security_cookie
0x18001d260  xor     rax, rsp
0x18001d263  mov     [rbp+90h+var_50], rax
0x18001d267  mov     r12, r8
0x18001d26a  mov     r15, rdx
0x18001d26d  mov     rsi, rcx
0x18001d270  xor     edi, edi
0x18001d272  mov     ebx, 80h
0x18001d277  mov     [rsp+190h+var_168], rdi
0x18001d27c  xor     r14d, r14d
0x18001d27f  mov     [rsp+190h+var_160], rdi
0x18001d284  mov     r8d, ebx; Size
0x18001d287  mov     [rsp+190h+var_170], r14
0x18001d28c  xor     edx, edx; Val
0x18001d28e  lea     rcx, [rsp+190h+var_150]; void *
0x18001d293  mov     r13, r9
0x18001d296  call    memset_0
0x18001d29b  mov     r8d, ebx; Size
0x18001d29e  lea     rcx, [rbp+90h+var_D0]; void *
0x18001d2a2  xor     edx, edx; Val
0x18001d2a4  call    memset_0
0x18001d2a9  xor     eax, eax
0x18001d2ab  test    r15, r15
0x18001d2ae  jnz     short loc_18001D2CD
0x18001d2b0  cmp     cs:?g_doStackCaptures@@3HA, eax; int g_doStackCaptures
0x18001d2b6  mov     ebx, 80070057h
0x18001d2bb  jz      loc_18001D36D
0x18001d2c1  mov     ecx, ebx; int
0x18001d2c3  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18001d2c8  jmp     loc_18001D36D
0x18001d2cd  test    r12, r12
0x18001d2d0  jz      short loc_18001D2B0
0x18001d2d2  test    r13, r13
0x18001d2d5  jz      short loc_18001D2B0
0x18001d2d7  mov     [r13+0], eax
0x18001d2db  mov     ebx, eax
0x18001d2dd  cmp     dword ptr [rsi+38h], 0Fh
0x18001d2e1  jz      loc_18001D36D
0x18001d2e7  lea     rdx, [rsp+190h+var_160]; void **
0x18001d2ec  mov     rcx, r15; struct IWICColorContext *
0x18001d2ef  call    ?GetProfileHandle@CIcmColorTransform@@SAJPEAUIWICColorContext@@PEAPEAX@Z; CIcmColorTransform::GetProfileHandle(IWICColorContext *,void * *)
0x18001d2f4  mov     r15, [rsp+190h+var_160]
0x18001d2f9  mov     ebx, eax
0x18001d2fb  test    eax, eax
0x18001d2fd  jns     short loc_18001D314
0x18001d2ff  xor     r12d, r12d
0x18001d302  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x18001d309  jz      short loc_18001D33F
0x18001d30b  mov     ecx, eax; int
0x18001d30d  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18001d312  jmp     short loc_18001D33F
0x18001d314  lea     rdx, [rsp+190h+var_170]; void **
0x18001d319  mov     rcx, r12; struct IWICColorContext *
0x18001d31c  call    ?GetProfileHandle@CIcmColorTransform@@SAJPEAUIWICColorContext@@PEAPEAX@Z; CIcmColorTransform::GetProfileHandle(IWICColorContext *,void * *)
0x18001d321  xor     r12d, r12d
0x18001d324  mov     ebx, eax
0x18001d326  test    eax, eax
0x18001d328  jns     short loc_18001D393
0x18001d32a  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x18001d331  jz      short loc_18001D38F
0x18001d333  mov     ecx, eax; int
0x18001d335  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18001d33a  mov     r14, [rsp+190h+var_170]
0x18001d33f  test    r15, r15
0x18001d342  jz      short loc_18001D34C
0x18001d344  mov     rcx, r15; void *
0x18001d347  call    ?CloseColorProfile@ICMModule@@SAHPEAX@Z; ICMModule::CloseColorProfile(void *)
0x18001d34c  test    r14, r14
0x18001d34f  jz      short loc_18001D359
0x18001d351  mov     rcx, r14; void *
0x18001d354  call    ?CloseColorProfile@ICMModule@@SAHPEAX@Z; ICMModule::CloseColorProfile(void *)
0x18001d359  test    rdi, rdi
0x18001d35c  jz      short loc_18001D36D
0x18001d35e  mov     rdx, [rdi]
0x18001d361  mov     rcx, rdi
0x18001d364  mov     rax, [rdx+10h]
0x18001d368  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d36d  mov     eax, ebx
0x18001d36f  mov     rcx, [rbp+90h+var_50]
0x18001d373  xor     rcx, rsp; StackCookie
0x18001d376  call    __security_check_cookie
0x18001d37b  add     rsp, 158h
0x18001d382  pop     r15
0x18001d384  pop     r14
0x18001d386  pop     r13
0x18001d388  pop     r12
0x18001d38a  pop     rdi
0x18001d38b  pop     rsi
0x18001d38c  pop     rbx
0x18001d38d  pop     rbp
0x18001d38e  retn
0x18001d38f  test    eax, eax
0x18001d391  js      short loc_18001D33A
0x18001d393  lea     rdx, [rsp+190h+var_150]; struct tagPROFILEHEADER *
0x18001d398  mov     rcx, r15; void *
0x18001d39b  call    ?GetColorProfileHeader@ICMModule@@SAHPEAXPEAUtagPROFILEHEADER@@@Z; ICMModule::GetColorProfileHeader(void *,tagPROFILEHEADER *)
0x18001d3a0  mov     r14, [rsp+190h+var_170]
0x18001d3a5  lea     rdx, [rbp+90h+var_D0]; struct tagPROFILEHEADER *
0x18001d3a9  mov     rcx, r14; void *
0x18001d3ac  call    ?GetColorProfileHeader@ICMModule@@SAHPEAXPEAUtagPROFILEHEADER@@@Z; ICMModule::GetColorProfileHeader(void *,tagPROFILEHEADER *)
0x18001d3b1  mov     eax, [rsp+190h+var_150.phDataColorSpace]
0x18001d3b5  mov     edx, 52474220h
0x18001d3ba  cmp     eax, 33434C52h
0x18001d3bf  jz      short loc_18001D417
0x18001d3c1  cmp     eax, 34434C52h
0x18001d3c6  jz      short loc_18001D410
0x18001d3c8  cmp     eax, 35434C52h
0x18001d3cd  jz      short loc_18001D409
0x18001d3cf  cmp     eax, 36434C52h
0x18001d3d4  jz      short loc_18001D402
0x18001d3d6  cmp     eax, 37434C52h
0x18001d3db  jz      short loc_18001D3FB
0x18001d3dd  cmp     eax, 38434C52h
0x18001d3e2  jz      short loc_18001D3F4
0x18001d3e4  cmp     eax, 434D594Bh
0x18001d3e9  jz      short loc_18001D410
0x18001d3eb  cmp     eax, edx
0x18001d3ed  jz      short loc_18001D417
0x18001d3ef  mov     ecx, r12d
0x18001d3f2  jmp     short loc_18001D41C
0x18001d3f4  mov     ecx, 8
0x18001d3f9  jmp     short loc_18001D41C
0x18001d3fb  mov     ecx, 7
0x18001d400  jmp     short loc_18001D41C
0x18001d402  mov     ecx, 6
0x18001d407  jmp     short loc_18001D41C
0x18001d409  mov     ecx, 5
0x18001d40e  jmp     short loc_18001D41C
0x18001d410  mov     ecx, 4
0x18001d415  jmp     short loc_18001D41C
0x18001d417  mov     ecx, 3
0x18001d41c  mov     eax, [rsi+44h]
0x18001d41f  sub     eax, [rsi+4Ch]
0x18001d422  cmp     ecx, eax
0x18001d424  jnz     loc_18001D33F
0x18001d42a  cmp     [rbp+90h+var_D0.phDataColorSpace], edx
0x18001d42d  jnz     loc_18001D33F
0x18001d433  lea     rcx, [rsp+190h+var_168]
0x18001d438  mov     dword ptr [rsp+190h+var_170], r12d
0x18001d43d  call    WICCreateIcmColorTransform
0x18001d442  mov     ebx, eax
0x18001d444  test    eax, eax
0x18001d446  jns     short loc_18001D462
0x18001d448  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x18001d44f  jz      short loc_18001D458
0x18001d451  mov     ecx, eax; int
0x18001d453  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18001d458  mov     rdi, [rsp+190h+var_168]
0x18001d45d  jmp     loc_18001D33F
0x18001d462  mov     rdi, [rsp+190h+var_168]
0x18001d467  mov     r8, r14
0x18001d46a  mov     rdx, r15
0x18001d46d  mov     rcx, rdi
0x18001d470  mov     rax, [rdi]
0x18001d473  mov     rax, [rax+48h]
0x18001d477  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d47c  mov     ebx, eax
0x18001d47e  test    eax, eax
0x18001d480  js      loc_18001D302
0x18001d486  mov     rcx, [rsi+88h]
0x18001d48d  test    rcx, rcx
0x18001d490  jz      short loc_18001D49E
0x18001d492  mov     rax, [rcx]
0x18001d495  mov     rax, [rax+10h]
0x18001d499  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d49e  mov     ecx, [rsi+38h]
0x18001d4a1  lea     rdx, [rsp+190h+var_170]
0x18001d4a6  mov     [rsi+88h], rdi
0x18001d4ad  mov     rdi, r12
0x18001d4b0  call    ?HrNChanPfToTableIndex@@YAJW4NChannelPixelFormat@@PEAI@Z; HrNChanPfToTableIndex(NChannelPixelFormat,uint *)
0x18001d4b5  mov     ebx, eax
0x18001d4b7  test    eax, eax
0x18001d4b9  jns     short loc_18001D4D0
0x18001d4bb  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x18001d4c2  jnz     loc_18001D30B
0x18001d4c8  test    eax, eax
0x18001d4ca  js      loc_18001D33F
0x18001d4d0  mov     eax, dword ptr [rsp+190h+var_170]
0x18001d4d4  lea     rcx, qword_180037D70
0x18001d4db  mov     eax, [rcx+rax*4]
0x18001d4de  mov     [rsi+40h], eax
0x18001d4e1  mov     eax, 1
0x18001d4e6  mov     [rsi+90h], eax
0x18001d4ec  mov     [r13+0], eax
0x18001d4f0  jmp     loc_18001D33F
```
