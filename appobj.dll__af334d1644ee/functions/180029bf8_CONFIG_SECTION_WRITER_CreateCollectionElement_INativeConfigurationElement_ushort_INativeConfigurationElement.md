# CONFIG_SECTION_WRITER::CreateCollectionElement(INativeConfigurationElement *,ushort *,INativeConfigurationElement * *)

- ea: `0x180029bf8`
- end: `0x180029f01`
- name: `?CreateCollectionElement@CONFIG_SECTION_WRITER@@AEAAJPEAVINativeConfigurationElement@@PEAGPEAPEAV2@@Z`
- size: `777`
- prototype: `__int64 __fastcall(CONFIG_SECTION_WRITER *this, struct INativeConfigurationElement *, unsigned __int16 *, struct INativeConfigurationElement **)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002a41c`

## callees

- `0x180001fb0`
- `0x180003280`
- `0x18001b140`
- `0x180029600`
- `0x1800298e4`
- `0x180029bf8`
- `0x180029f08`
- `0x18002a0b8`
- `0x180034cbe`
- `0x180034d00`
- `0x180036010`

## pseudocode

```c
__int64 __fastcall CONFIG_SECTION_WRITER::CreateCollectionElement(
        CONFIG_SECTION_WRITER *this,
        struct INativeConfigurationElement *a2,
        unsigned __int16 *a3,
        struct INativeConfigurationElement **a4)
{
  int v7; // esi
  CONFIG_SECTION_WRITER *v8; // rcx
  int v9; // ebx
  unsigned int i; // edi
  struct INativeConfigurationElement *v11; // rdi
  int v12; // esi
  unsigned __int16 *v13; // rbx
  int IsBuiltInAttribute; // eax
  __int64 v15; // r11
  unsigned __int16 *v16; // r8
  int v17; // eax
  struct INativeConfigurationElement *v19; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v20; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v21; // [rsp+40h] [rbp-C0h] BYREF
  int v22; // [rsp+44h] [rbp-BCh] BYREF
  unsigned __int16 *v23; // [rsp+48h] [rbp-B8h] BYREF
  void **v24; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v25; // [rsp+58h] [rbp-A8h]
  int v26; // [rsp+5Ch] [rbp-A4h]
  char *v27; // [rsp+60h] [rbp-A0h]
  char v28; // [rsp+68h] [rbp-98h] BYREF
  char *v29; // [rsp+90h] [rbp-70h]
  char v30; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v31[32]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE *v32; // [rsp+E0h] [rbp-20h]
  int v33; // [rsp+E8h] [rbp-18h]
  __int16 v34; // [rsp+ECh] [rbp-14h]
  int v35; // [rsp+F0h] [rbp-10h]
  _BYTE v36[64]; // [rsp+100h] [rbp+0h] BYREF

  v20 = 0;
  v19 = 0;
  memset_0(v36, 0, sizeof(v36));
  v33 = 64;
  v32 = v36;
  v24 = &COLLECTION_CONDITIONS::`vftable';
  v27 = &v28;
  v29 = &v30;
  v7 = 0;
  v34 = 256;
  v35 = 0;
  v25 = 0;
  v26 = 5;
  v21 = 0;
  v23 = 0;
  if ( !a2 || !a3 || !a4 || *a4 )
  {
    v9 = -2147024809;
    goto LABEL_36;
  }
  v9 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, __int64 *))(*(_QWORD *)a2 + 40LL))(a2, &v20);
  if ( v9 >= 0 )
  {
    v9 = CONFIG_SECTION_WRITER::ParseCollectionElementSpecifier(
           v8,
           a3,
           (struct STRU *)v31,
           (struct COLLECTION_CONDITIONS *)&v24);
    if ( v9 >= 0 )
    {
      v9 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v20 + 72LL))(v20, &v21);
      if ( v9 >= 0 )
      {
        for ( i = 0; i < v21; ++i )
        {
          v9 = (*(__int64 (__fastcall **)(__int64, _QWORD, struct INativeConfigurationElement **))(*(_QWORD *)v20 + 80LL))(
                 v20,
                 i,
                 &v19);
          if ( v9 < 0 )
            goto LABEL_29;
          v23 = 0;
          v9 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, unsigned __int16 **))(*(_QWORD *)v19 + 24LL))(
                 v19,
                 &v23);
          if ( v9 < 0 )
            goto LABEL_29;
          if ( STRU::Equals((STRU *)v31, v23) )
          {
            v22 = 0;
            v9 = COLLECTION_CONDITIONS::CompareToCollectionElement((COLLECTION_CONDITIONS *)&v24, v19, &v22);
            if ( v9 < 0 )
              goto LABEL_29;
            v7 = v22;
            if ( v22 )
              goto LABEL_28;
          }
          (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v19 + 16LL))(v19);
          v19 = 0;
        }
        if ( !v7 )
        {
          v9 = (*(__int64 (__fastcall **)(__int64, _BYTE *, struct INativeConfigurationElement **))(*(_QWORD *)v20 + 48LL))(
                 v20,
                 v32,
                 &v19);
          if ( v9 < 0 )
            goto LABEL_29;
          v11 = v19;
          if ( !v19 )
          {
            v9 = -2147024809;
            goto LABEL_30;
          }
          v12 = 0;
          if ( v25 )
          {
            while ( 1 )
            {
              v13 = *(unsigned __int16 **)&v27[8 * v12];
              IsBuiltInAttribute = CONFIG_OBJECT_EXTENSION::IsBuiltInAttribute(v13);
              v16 = *(unsigned __int16 **)&v29[8 * v15];
              v17 = IsBuiltInAttribute
                  ? CONFIG_SECTION_WRITER::WriteBuiltInAttribute(v11, v13, v16)
                  : (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, unsigned __int16 *, unsigned __int16 *, _QWORD))(*(_QWORD *)v11 + 160LL))(
                      v11,
                      v13,
                      v16,
                      0);
              v9 = v17;
              if ( v17 < 0 )
                goto LABEL_29;
              if ( ++v12 >= v25 )
              {
                v11 = v19;
                break;
              }
            }
          }
          v9 = (*(__int64 (__fastcall **)(__int64, struct INativeConfigurationElement *, __int64, _QWORD))(*(_QWORD *)v20 + 88LL))(
                 v20,
                 v11,
                 0xFFFFFFFFLL,
                 0);
          if ( v9 < 0 )
            goto LABEL_29;
        }
LABEL_28:
        *a4 = v19;
        goto LABEL_32;
      }
    }
  }
LABEL_29:
  v11 = v19;
LABEL_30:
  if ( v11 )
  {
    (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v11 + 16LL))(v11);
LABEL_32:
    v19 = 0;
  }
  if ( v20 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    v20 = 0;
  }
LABEL_36:
  COLLECTION_CONDITIONS::~COLLECTION_CONDITIONS((COLLECTION_CONDITIONS *)&v24);
  BUFFER::~BUFFER((BUFFER *)v31);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180029bf8  mov     [rsp-8+arg_0], rbx
0x180029bfd  push    rbp
0x180029bfe  push    rsi
0x180029bff  push    rdi
0x180029c00  push    r14
0x180029c02  push    r15
0x180029c04  lea     rbp, [rsp-50h]
0x180029c09  sub     rsp, 150h
0x180029c10  mov     rax, cs:__security_cookie
0x180029c17  xor     rax, rsp
0x180029c1a  mov     [rbp+70h+var_30], rax
0x180029c1e  xor     r15d, r15d
0x180029c21  lea     rcx, [rbp+70h+var_70]; void *
0x180029c25  mov     rdi, r8
0x180029c28  mov     [rsp+170h+var_138], r15
0x180029c2d  mov     rbx, rdx
0x180029c30  mov     [rsp+170h+var_140], r15
0x180029c35  xor     edx, edx; Val
0x180029c37  mov     r14, r9
0x180029c3a  lea     esi, [r15+40h]
0x180029c3e  mov     r8d, esi; Size
0x180029c41  call    memset_0
0x180029c46  mov     [rbp+70h+var_88], esi
0x180029c49  lea     rax, [rbp+70h+var_70]
0x180029c4d  mov     [rbp+70h+var_90], rax
0x180029c51  lea     rax, ??_7COLLECTION_CONDITIONS@@6B@; const COLLECTION_CONDITIONS::`vftable'
0x180029c58  mov     [rsp+170h+var_120], rax
0x180029c5d  lea     rax, [rsp+170h+var_108]
0x180029c62  mov     [rsp+170h+var_110], rax
0x180029c67  lea     rax, [rbp+70h+var_D8]
0x180029c6b  mov     [rbp+70h+var_E0], rax
0x180029c6f  mov     esi, r15d
0x180029c72  mov     [rbp+70h+var_84], 100h
0x180029c78  mov     [rbp+70h+var_80], r15d
0x180029c7c  mov     [rsp+170h+var_118], r15d
0x180029c81  mov     [rsp+170h+var_114], 5
0x180029c89  mov     [rsp+170h+var_130], r15d
0x180029c8e  mov     [rsp+170h+var_128], r15
0x180029c93  test    rbx, rbx
0x180029c96  jz      loc_180029EC4
0x180029c9c  test    rdi, rdi
0x180029c9f  jz      loc_180029EC4
0x180029ca5  test    r14, r14
0x180029ca8  jz      loc_180029EC4
0x180029cae  cmp     [r14], r15
0x180029cb1  jnz     loc_180029EC4
0x180029cb7  mov     rax, [rbx]
0x180029cba  lea     rdx, [rsp+170h+var_138]
0x180029cbf  mov     rcx, rbx
0x180029cc2  mov     rax, [rax+28h]
0x180029cc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029ccb  mov     ebx, eax
0x180029ccd  test    eax, eax
0x180029ccf  js      loc_180029E89
0x180029cd5  lea     r9, [rsp+170h+var_120]; struct COLLECTION_CONDITIONS *
0x180029cda  mov     rdx, rdi; unsigned __int16 *
0x180029cdd  lea     r8, [rbp+70h+var_B0]; struct STRU *
0x180029ce1  call    ?ParseCollectionElementSpecifier@CONFIG_SECTION_WRITER@@AEAAJPEAGPEAVSTRU@@PEAVCOLLECTION_CONDITIONS@@@Z; CONFIG_SECTION_WRITER::ParseCollectionElementSpecifier(ushort *,STRU *,COLLECTION_CONDITIONS *)
0x180029ce6  mov     ebx, eax
0x180029ce8  test    eax, eax
0x180029cea  js      loc_180029E89
0x180029cf0  mov     rcx, [rsp+170h+var_138]
0x180029cf5  lea     rdx, [rsp+170h+var_130]
0x180029cfa  mov     rax, [rcx]
0x180029cfd  mov     rax, [rax+48h]
0x180029d01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029d06  mov     ebx, eax
0x180029d08  test    eax, eax
0x180029d0a  js      loc_180029E89
0x180029d10  mov     edi, r15d
0x180029d13  cmp     edi, [rsp+170h+var_130]
0x180029d17  jnb     loc_180029DC2
0x180029d1d  mov     rcx, [rsp+170h+var_138]
0x180029d22  lea     r8, [rsp+170h+var_140]
0x180029d27  mov     edx, edi
0x180029d29  mov     rax, [rcx]
0x180029d2c  mov     rax, [rax+50h]
0x180029d30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029d35  mov     ebx, eax
0x180029d37  test    eax, eax
0x180029d39  js      loc_180029E89
0x180029d3f  mov     rcx, [rsp+170h+var_140]
0x180029d44  lea     rdx, [rsp+170h+var_128]
0x180029d49  mov     [rsp+170h+var_128], r15
0x180029d4e  mov     rax, [rcx]
0x180029d51  mov     rax, [rax+18h]
0x180029d55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029d5a  mov     ebx, eax
0x180029d5c  test    eax, eax
0x180029d5e  js      loc_180029E89
0x180029d64  mov     rdx, [rsp+170h+var_128]; unsigned __int16 *
0x180029d69  lea     rcx, [rbp+70h+var_B0]; this
0x180029d6d  call    ?Equals@STRU@@QEBA_NPEBG@Z; STRU::Equals(ushort const *)
0x180029d72  test    al, al
0x180029d74  jz      short loc_180029DA5
0x180029d76  mov     rdx, [rsp+170h+var_140]; struct INativeConfigurationElement *
0x180029d7b  lea     r8, [rsp+170h+var_12C]; int *
0x180029d80  lea     rcx, [rsp+170h+var_120]; this
0x180029d85  mov     [rsp+170h+var_12C], r15d
0x180029d8a  call    ?CompareToCollectionElement@COLLECTION_CONDITIONS@@QEAAJPEAVINativeConfigurationElement@@PEAH@Z; COLLECTION_CONDITIONS::CompareToCollectionElement(INativeConfigurationElement *,int *)
0x180029d8f  mov     ebx, eax
0x180029d91  test    eax, eax
0x180029d93  js      loc_180029E89
0x180029d99  mov     esi, [rsp+170h+var_12C]
0x180029d9d  test    esi, esi
0x180029d9f  jnz     loc_180029E7F
0x180029da5  mov     rcx, [rsp+170h+var_140]
0x180029daa  mov     rax, [rcx]
0x180029dad  mov     rax, [rax+10h]
0x180029db1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029db6  inc     edi
0x180029db8  mov     [rsp+170h+var_140], r15
0x180029dbd  jmp     loc_180029D13
0x180029dc2  test    esi, esi
0x180029dc4  jnz     loc_180029E7F
0x180029dca  mov     rcx, [rsp+170h+var_138]
0x180029dcf  lea     r8, [rsp+170h+var_140]
0x180029dd4  mov     rdx, [rbp+70h+var_90]
0x180029dd8  mov     rax, [rcx]
0x180029ddb  mov     rax, [rax+30h]
0x180029ddf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029de4  mov     ebx, eax
0x180029de6  test    eax, eax
0x180029de8  js      loc_180029E89
0x180029dee  mov     rdi, [rsp+170h+var_140]
0x180029df3  test    rdi, rdi
0x180029df6  jnz     short loc_180029E02
0x180029df8  mov     ebx, 80070057h
0x180029dfd  jmp     loc_180029E8E
0x180029e02  mov     esi, r15d
0x180029e05  cmp     [rsp+170h+var_118], r15d
0x180029e0a  jbe     short loc_180029E5E
0x180029e0c  mov     rax, [rsp+170h+var_110]
0x180029e11  mov     r11d, esi
0x180029e14  mov     rbx, [rax+r11*8]
0x180029e18  mov     rcx, rbx; unsigned __int16 *
0x180029e1b  call    ?IsBuiltInAttribute@CONFIG_OBJECT_EXTENSION@@SAHPEAG@Z; CONFIG_OBJECT_EXTENSION::IsBuiltInAttribute(ushort *)
0x180029e20  mov     r8, [rbp+70h+var_E0]
0x180029e24  mov     rdx, rbx; unsigned __int16 *
0x180029e27  mov     rcx, rdi; struct INativeConfigurationElement *
0x180029e2a  mov     r8, [r8+r11*8]; unsigned __int16 *
0x180029e2e  test    eax, eax
0x180029e30  jz      short loc_180029E39
0x180029e32  call    ?WriteBuiltInAttribute@CONFIG_SECTION_WRITER@@SAJPEAVINativeConfigurationElement@@PEAG1@Z; CONFIG_SECTION_WRITER::WriteBuiltInAttribute(INativeConfigurationElement *,ushort *,ushort *)
0x180029e37  jmp     short loc_180029E4B
0x180029e39  mov     rax, [rdi]
0x180029e3c  xor     r9d, r9d
0x180029e3f  mov     rax, [rax+0A0h]
0x180029e46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029e4b  mov     ebx, eax
0x180029e4d  test    eax, eax
0x180029e4f  js      short loc_180029E89
0x180029e51  inc     esi
0x180029e53  cmp     esi, [rsp+170h+var_118]
0x180029e57  jb      short loc_180029E0C
0x180029e59  mov     rdi, [rsp+170h+var_140]
0x180029e5e  mov     rcx, [rsp+170h+var_138]
0x180029e63  xor     r9d, r9d
0x180029e66  or      r8d, 0FFFFFFFFh
0x180029e6a  mov     rdx, rdi
0x180029e6d  mov     rax, [rcx]
0x180029e70  mov     rax, [rax+58h]
0x180029e74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029e79  mov     ebx, eax
0x180029e7b  test    eax, eax
0x180029e7d  js      short loc_180029E89
0x180029e7f  mov     rax, [rsp+170h+var_140]
0x180029e84  mov     [r14], rax
0x180029e87  jmp     short loc_180029EA2
0x180029e89  mov     rdi, [rsp+170h+var_140]
0x180029e8e  test    rdi, rdi
0x180029e91  jz      short loc_180029EA7
0x180029e93  mov     rax, [rdi]
0x180029e96  mov     rcx, rdi
0x180029e99  mov     rax, [rax+10h]
0x180029e9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029ea2  mov     [rsp+170h+var_140], r15
0x180029ea7  mov     rcx, [rsp+170h+var_138]
0x180029eac  test    rcx, rcx
0x180029eaf  jz      short loc_180029EC9
0x180029eb1  mov     rax, [rcx]
0x180029eb4  mov     rax, [rax+10h]
0x180029eb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029ebd  mov     [rsp+170h+var_138], r15
0x180029ec2  jmp     short loc_180029EC9
0x180029ec4  mov     ebx, 80070057h
0x180029ec9  lea     rcx, [rsp+170h+var_120]; this
0x180029ece  call    ??1COLLECTION_CONDITIONS@@UEAA@XZ; COLLECTION_CONDITIONS::~COLLECTION_CONDITIONS(void)
0x180029ed3  lea     rcx, [rbp+70h+var_B0]; this
0x180029ed7  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180029edc  mov     eax, ebx
0x180029ede  mov     rcx, [rbp+70h+var_30]
0x180029ee2  xor     rcx, rsp; StackCookie
0x180029ee5  call    __security_check_cookie
0x180029eea  mov     rbx, [rsp+170h+arg_0]
0x180029ef2  add     rsp, 150h
0x180029ef9  pop     r15
0x180029efb  pop     r14
0x180029efd  pop     rdi
0x180029efe  pop     rsi
0x180029eff  pop     rbp
0x180029f00  retn
```
