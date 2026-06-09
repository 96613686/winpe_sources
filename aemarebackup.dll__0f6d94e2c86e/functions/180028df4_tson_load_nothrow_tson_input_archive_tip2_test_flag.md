# tson::load_nothrow(tson::input_archive &,tip2::test_flag &)

- ea: `0x180028df4`
- end: `0x1800293c4`
- name: `?load_nothrow@tson@@YAXAEAVinput_archive@1@AEAUtest_flag@tip2@@@Z`
- size: `1488`
- prototype: `void __fastcall(tson *__hidden this, struct tson::input_archive *, struct tip2::test_flag *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x1800119f4`

## callees

- `0x18000f1d4`
- `0x180011440`
- `0x180011800`
- `0x180028ccc`
- `0x180028df4`
- `0x18002a320`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x18002924d`
- `ole32!CoTaskMemAlloc` at `0x18002924d`

## pseudocode

```c
void __fastcall tson::load_nothrow(tson *this, struct tson::input_archive *a2, struct tip2::test_flag *a3)
{
  unsigned __int16 *v3; // rbx
  __int64 v6; // r8
  __int64 v7; // r8
  unsigned int v8; // ecx
  unsigned int v9; // ecx
  unsigned int v10; // ecx
  unsigned int v11; // ecx
  unsigned int v12; // ecx
  __int64 v13; // rcx
  _BYTE *v14; // rdx
  __int64 v15; // rdx
  char *v16; // rax
  char v17; // cl
  __int64 v18; // rcx
  _BYTE *v19; // rdx
  __int64 v20; // rdx
  char *v21; // rax
  char v22; // cl
  char v23; // al
  __int16 v24; // ax
  __int64 v25; // rcx
  _BYTE *v26; // rdx
  bool v27; // zf
  __int64 v28; // rcx
  _QWORD *v29; // rdx
  __int64 v30; // rcx
  _BYTE *v31; // rdx
  bool v32; // zf
  _DWORD *v33; // rdx
  __int64 v34; // rcx
  _BYTE *v35; // rdx
  _WORD *v36; // rdx
  __int64 v37; // rcx
  _BYTE *v38; // rdx
  char *v39; // rax
  char v40; // cl
  unsigned int v41; // ecx
  unsigned int v42; // ecx
  unsigned int v43; // ecx
  unsigned int v44; // ecx
  unsigned int v45; // ecx
  const char *v46; // rax
  const char *v47; // rbx
  void *v48; // rax
  _BYTE *v49; // rdx
  _BYTE *v50; // rdx
  _BYTE *v51; // rdx
  _QWORD v52[2]; // [rsp+20h] [rbp-60h] BYREF
  const char *v53; // [rsp+30h] [rbp-50h] BYREF
  __int64 v54; // [rsp+38h] [rbp-48h]
  struct tson::input_archive *v55; // [rsp+40h] [rbp-40h]
  const char *v56; // [rsp+48h] [rbp-38h] BYREF
  char v57; // [rsp+50h] [rbp-30h]
  _QWORD *v58; // [rsp+58h] [rbp-28h]
  const char *v59; // [rsp+60h] [rbp-20h] BYREF
  char v60; // [rsp+68h] [rbp-18h]
  char *v61; // [rsp+70h] [rbp-10h]
  void *v62; // [rsp+A8h] [rbp+28h] BYREF

  v55 = a2;
  *((_QWORD *)a2 + 1) = (char *)a2 + 40;
  v3 = (unsigned __int16 *)((char *)a2 + 16);
  v52[0] = (char *)a2 + 40;
  v52[1] = 64;
  v59 = "type";
  v60 = 4;
  v56 = "name";
  v61 = (char *)a2 + 16;
  v58 = v52;
  v53 = "reason";
  v57 = 4;
  LOBYTE(v54) = 6;
  tson::input_archive::process<tson::nvp<unsigned short &>>(this, &v53, a3);
  tson::input_archive::process<tson::nvp<tson::ansistring_buffer_tag &>>(this, &v56);
  tson::input_archive::process<tson::nvp<unsigned short &>>(this, &v59, v6);
  v8 = *v3;
  if ( v8 > 0x11 )
  {
    v41 = v8 - 18;
    if ( !v41 )
    {
      v60 = 5;
      v59 = "value";
      v61 = (char *)a2 + 24;
      tson::input_archive::process<tson::nvp<unsigned short &>>(this, &v59, v7);
      return;
    }
    v42 = v41 - 1;
    if ( !v42 )
    {
      *((_BYTE *)this + 24) = 5;
      *((_QWORD *)this + 2) = "value";
      if ( tson::input_archive::search(this) )
      {
        v30 = *(_QWORD *)this;
        v51 = *(_BYTE **)(*(_QWORD *)this + 8LL);
        if ( (unsigned __int64)v51 < *(_QWORD *)(*(_QWORD *)this + 16LL) )
        {
          *(_QWORD *)(v30 + 8) = v51 + 1;
          if ( !v51 )
            goto LABEL_53;
          v32 = *v51 == 18;
LABEL_49:
          if ( !v32 && *((int *)this + 2) >= 0 )
            *((_DWORD *)this + 2) = -2147023267;
LABEL_53:
          v28 = *(_QWORD *)this;
          v33 = *(_DWORD **)(*(_QWORD *)this + 8LL);
          if ( (unsigned __int64)(v33 + 1) <= *(_QWORD *)(*(_QWORD *)this + 16LL) )
          {
            *((_DWORD *)a2 + 6) = *v33;
            *(_QWORD *)(v28 + 8) += 4LL;
            return;
          }
          goto LABEL_44;
        }
LABEL_52:
        *(_BYTE *)(v30 + 24) = 1;
        goto LABEL_53;
      }
LABEL_55:
      *((_DWORD *)a2 + 6) = 0;
      return;
    }
    v43 = v42 - 1;
    if ( !v43 )
    {
      *((_BYTE *)this + 24) = 5;
      *((_QWORD *)this + 2) = "value";
      if ( tson::input_archive::search(this) )
      {
        v25 = *(_QWORD *)this;
        v50 = *(_BYTE **)(*(_QWORD *)this + 8LL);
        if ( (unsigned __int64)v50 < *(_QWORD *)(*(_QWORD *)this + 16LL) )
        {
          *(_QWORD *)(v25 + 8) = v50 + 1;
          if ( !v50 )
            goto LABEL_42;
          v27 = *v50 == 19;
LABEL_38:
          if ( !v27 && *((int *)this + 2) >= 0 )
            *((_DWORD *)this + 2) = -2147023267;
LABEL_42:
          v28 = *(_QWORD *)this;
          v29 = *(_QWORD **)(*(_QWORD *)this + 8LL);
          if ( (unsigned __int64)(v29 + 1) <= *(_QWORD *)(*(_QWORD *)this + 16LL) )
          {
            *((_QWORD *)a2 + 3) = *v29;
            *(_QWORD *)(v28 + 8) += 8LL;
            return;
          }
          goto LABEL_44;
        }
LABEL_41:
        *(_BYTE *)(v25 + 24) = 1;
        goto LABEL_42;
      }
      goto LABEL_101;
    }
    v44 = v43 - 1;
    if ( !v44 )
    {
      *((_BYTE *)this + 24) = 5;
      *((_QWORD *)this + 2) = "value";
      if ( tson::input_archive::search(this) )
      {
        v25 = *(_QWORD *)this;
        v49 = *(_BYTE **)(*(_QWORD *)this + 8LL);
        if ( (unsigned __int64)v49 < *(_QWORD *)(*(_QWORD *)this + 16LL) )
        {
          *(_QWORD *)(v25 + 8) = v49 + 1;
          if ( !v49 )
            goto LABEL_42;
          v27 = *v49 == 20;
          goto LABEL_38;
        }
        goto LABEL_41;
      }
LABEL_101:
      v48 = 0;
      goto LABEL_102;
    }
    v45 = v44 - 9;
    if ( !v45 )
    {
      v62 = 0;
      *((_QWORD *)this + 2) = "value";
      *((_BYTE *)this + 24) = 5;
      tson::input_archive::operator()<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>> &>(
        this,
        &v62);
      v48 = v62;
LABEL_102:
      *((_QWORD *)a2 + 3) = v48;
      return;
    }
    if ( v45 != 1 )
      goto LABEL_83;
    *((_BYTE *)this + 24) = 5;
    *((_QWORD *)this + 2) = "value";
    v53 = 0;
    v55 = 0;
    v54 = 0;
    tson::input_archive::loadValue(this, (struct tson::string_tag *)&v53);
    if ( v54 )
    {
      v46 = (const char *)CoTaskMemAlloc(2 * v54);
      v47 = v46;
      if ( v46 )
      {
        v53 = v46;
        tson::input_archive::loadValue(this, (struct tson::string_tag *)&v53);
LABEL_91:
        *((_QWORD *)a2 + 3) = v47;
        return;
      }
      if ( *((int *)this + 2) >= 0 )
        *((_DWORD *)this + 2) = -2147024882;
    }
    v47 = 0;
    goto LABEL_91;
  }
  if ( v8 != 17 )
  {
    if ( !*v3 )
      return;
    v9 = v8 - 2;
    if ( !v9 )
    {
      *((_BYTE *)this + 24) = 5;
      *((_QWORD *)this + 2) = "value";
      if ( !tson::input_archive::search(this) )
      {
        v24 = 0;
        goto LABEL_66;
      }
      v34 = *(_QWORD *)this;
      v35 = *(_BYTE **)(*(_QWORD *)this + 8LL);
      if ( (unsigned __int64)v35 >= *(_QWORD *)(*(_QWORD *)this + 16LL) )
      {
        *(_BYTE *)(v34 + 24) = 1;
      }
      else
      {
        *(_QWORD *)(v34 + 8) = v35 + 1;
        if ( v35 && *v35 != 13 && *((int *)this + 2) >= 0 )
          *((_DWORD *)this + 2) = -2147023267;
      }
      v28 = *(_QWORD *)this;
      v36 = *(_WORD **)(*(_QWORD *)this + 8LL);
      if ( (unsigned __int64)(v36 + 1) <= *(_QWORD *)(*(_QWORD *)this + 16LL) )
      {
        *((_WORD *)a2 + 12) = *v36;
        *(_QWORD *)(v28 + 8) += 2LL;
        return;
      }
LABEL_44:
      *(_BYTE *)(v28 + 24) = 1;
      return;
    }
    v10 = v9 - 1;
    if ( v10 )
    {
      v11 = v10 - 2;
      if ( v11 )
      {
        v12 = v11 - 6;
        if ( v12 )
        {
          if ( v12 == 5 )
          {
            *((_BYTE *)this + 24) = 5;
            *((_QWORD *)this + 2) = "value";
            if ( tson::input_archive::search(this) )
            {
              v13 = *(_QWORD *)this;
              v14 = *(_BYTE **)(*(_QWORD *)this + 8LL);
              if ( (unsigned __int64)v14 >= *(_QWORD *)(*(_QWORD *)this + 16LL) )
              {
                *(_BYTE *)(v13 + 24) = 1;
              }
              else
              {
                *(_QWORD *)(v13 + 8) = v14 + 1;
                if ( v14 && *v14 != 11 && *((int *)this + 2) >= 0 )
                  *((_DWORD *)this + 2) = -2147023267;
              }
              v15 = *(_QWORD *)this;
              v16 = *(char **)(*(_QWORD *)this + 8LL);
              if ( (unsigned __int64)v16 < *(_QWORD *)(*(_QWORD *)this + 16LL) )
              {
                v17 = *v16;
                *(_QWORD *)(v15 + 8) = v16 + 1;
                *((_BYTE *)v3 + 8) = v17;
                return;
              }
              goto LABEL_18;
            }
            *((_BYTE *)v3 + 8) = 0;
            return;
          }
LABEL_83:
          if ( *((int *)this + 2) >= 0 )
            *((_DWORD *)this + 2) = -2147024119;
          return;
        }
        LOBYTE(v62) = 0;
        *((_QWORD *)this + 2) = "value";
        *((_BYTE *)this + 24) = 5;
        if ( tson::input_archive::search(this) )
        {
          v18 = *(_QWORD *)this;
          v19 = *(_BYTE **)(*(_QWORD *)this + 8LL);
          if ( (unsigned __int64)v19 >= *(_QWORD *)(*(_QWORD *)this + 16LL) )
          {
            *(_BYTE *)(v18 + 24) = 1;
          }
          else
          {
            *(_QWORD *)(v18 + 8) = v19 + 1;
            if ( v19 && *v19 != 10 && *((int *)this + 2) >= 0 )
              *((_DWORD *)this + 2) = -2147023267;
          }
          v20 = *(_QWORD *)this;
          v21 = *(char **)(*(_QWORD *)this + 8LL);
          if ( (unsigned __int64)v21 >= *(_QWORD *)(*(_QWORD *)this + 16LL) )
          {
            *(_BYTE *)(v20 + 24) = 1;
            v23 = (char)v62;
          }
          else
          {
            v22 = *v21;
            *(_QWORD *)(v20 + 8) = v21 + 1;
            v23 = v22 != 0;
          }
        }
        else
        {
          v23 = 0;
        }
        if ( v23 )
          v24 = -1;
        else
          v24 = 0;
LABEL_66:
        *((_WORD *)a2 + 12) = v24;
        return;
      }
      *((_BYTE *)this + 24) = 5;
      *((_QWORD *)this + 2) = "value";
      if ( tson::input_archive::search(this) )
      {
        v25 = *(_QWORD *)this;
        v26 = *(_BYTE **)(*(_QWORD *)this + 8LL);
        if ( (unsigned __int64)v26 < *(_QWORD *)(*(_QWORD *)this + 16LL) )
        {
          *(_QWORD *)(v25 + 8) = v26 + 1;
          if ( !v26 )
            goto LABEL_42;
          v27 = *v26 == 21;
          goto LABEL_38;
        }
        goto LABEL_41;
      }
      goto LABEL_101;
    }
    *((_BYTE *)this + 24) = 5;
    *((_QWORD *)this + 2) = "value";
    if ( tson::input_archive::search(this) )
    {
      v30 = *(_QWORD *)this;
      v31 = *(_BYTE **)(*(_QWORD *)this + 8LL);
      if ( (unsigned __int64)v31 < *(_QWORD *)(*(_QWORD *)this + 16LL) )
      {
        *(_QWORD *)(v30 + 8) = v31 + 1;
        if ( !v31 )
          goto LABEL_53;
        v32 = *v31 == 17;
        goto LABEL_49;
      }
      goto LABEL_52;
    }
    goto LABEL_55;
  }
  *((_BYTE *)this + 24) = 5;
  *((_QWORD *)this + 2) = "value";
  if ( tson::input_archive::search(this) )
  {
    v37 = *(_QWORD *)this;
    v38 = *(_BYTE **)(*(_QWORD *)this + 8LL);
    if ( (unsigned __int64)v38 >= *(_QWORD *)(*(_QWORD *)this + 16LL) )
    {
      *(_BYTE *)(v37 + 24) = 1;
    }
    else
    {
      *(_QWORD *)(v37 + 8) = v38 + 1;
      if ( v38 && *v38 != 12 && *((int *)this + 2) >= 0 )
        *((_DWORD *)this + 2) = -2147023267;
    }
    v15 = *(_QWORD *)this;
    v39 = *(char **)(*(_QWORD *)this + 8LL);
    if ( (unsigned __int64)v39 >= *(_QWORD *)(*(_QWORD *)this + 16LL) )
    {
LABEL_18:
      *(_BYTE *)(v15 + 24) = 1;
      return;
    }
    v40 = *v39;
    *(_QWORD *)(v15 + 8) = v39 + 1;
    *((_BYTE *)a2 + 24) = v40;
  }
  else
  {
    *((_BYTE *)a2 + 24) = 0;
  }
}

```

## disassembly

```asm
0x180028df4  mov     [rsp-18h+arg_0], rbx
0x180028df9  mov     [rsp-18h+arg_10], rsi
0x180028dfe  push    rbp
0x180028dff  push    rdi
0x180028e00  push    r14
0x180028e02  mov     rbp, rsp
0x180028e05  sub     rsp, 80h
0x180028e0c  lea     rax, [rdx+28h]
0x180028e10  mov     [rbp+var_40], rdx
0x180028e14  mov     [rdx+8], rax
0x180028e18  lea     rbx, [rdx+10h]
0x180028e1c  mov     [rbp+var_60], rax
0x180028e20  mov     rsi, rdx
0x180028e23  lea     rax, aType_0; "type"
0x180028e2a  mov     [rbp+var_58], 40h ; '@'
0x180028e32  mov     [rbp+var_20], rax
0x180028e36  lea     rdx, [rbp+var_50]
0x180028e3a  lea     rax, aName_0; "name"
0x180028e41  mov     [rbp+var_18], 4
0x180028e45  mov     [rbp+var_38], rax
0x180028e49  mov     rdi, rcx
0x180028e4c  lea     rax, [rbp+var_60]
0x180028e50  mov     [rbp+var_10], rbx
0x180028e54  mov     [rbp+var_28], rax
0x180028e58  lea     rax, aReason; "reason"
0x180028e5f  mov     [rbp+var_50], rax
0x180028e63  mov     [rbp+var_30], 4
0x180028e67  mov     byte ptr [rbp+var_48], 6
0x180028e6b  call    ??$process@V?$nvp@AEAG@tson@@@input_archive@tson@@AEAAX$$QEAV?$nvp@AEAG@1@@Z; tson::input_archive::process<tson::nvp<ushort &>>(tson::nvp<ushort &> &&)
0x180028e70  lea     rdx, [rbp+var_38]
0x180028e74  mov     rcx, rdi
0x180028e77  call    ??$process@V?$nvp@AEAUansistring_buffer_tag@tson@@@tson@@@input_archive@tson@@AEAAX$$QEAV?$nvp@AEAUansistring_buffer_tag@tson@@@1@@Z; tson::input_archive::process<tson::nvp<tson::ansistring_buffer_tag &>>(tson::nvp<tson::ansistring_buffer_tag &> &&)
0x180028e7c  lea     rdx, [rbp+var_20]
0x180028e80  mov     rcx, rdi
0x180028e83  call    ??$process@V?$nvp@AEAG@tson@@@input_archive@tson@@AEAAX$$QEAV?$nvp@AEAG@1@@Z; tson::input_archive::process<tson::nvp<ushort &>>(tson::nvp<ushort &> &&)
0x180028e88  movzx   ecx, word ptr [rbx]
0x180028e8b  xor     r14d, r14d
0x180028e8e  cmp     ecx, 11h
0x180028e91  ja      loc_1800291C6
0x180028e97  jz      loc_18002914D
0x180028e9d  test    ecx, ecx
0x180028e9f  jz      loc_1800293AC
0x180028ea5  sub     ecx, 2
0x180028ea8  jz      loc_1800290CF
0x180028eae  sub     ecx, 1
0x180028eb1  jz      loc_180029058
0x180028eb7  sub     ecx, 2
0x180028eba  jz      loc_180028FDC
0x180028ec0  sub     ecx, 6
0x180028ec3  jz      loc_180028F4F
0x180028ec9  cmp     ecx, 5
0x180028ecc  jnz     loc_1800291F8
0x180028ed2  lea     rax, aValue; "value"
0x180028ed9  mov     [rdi+18h], cl
0x180028edc  mov     rcx, rdi; this
0x180028edf  mov     [rdi+10h], rax
0x180028ee3  call    ?search@input_archive@tson@@AEAA_NXZ; tson::input_archive::search(void)
0x180028ee8  test    al, al
0x180028eea  jz      short loc_180028F45
0x180028eec  mov     rcx, [rdi]
0x180028eef  mov     rdx, [rcx+8]
0x180028ef3  cmp     rdx, [rcx+10h]
0x180028ef7  jnb     short loc_180028F1A
0x180028ef9  lea     rax, [rdx+1]
0x180028efd  mov     [rcx+8], rax
0x180028f01  test    rdx, rdx
0x180028f04  jz      short loc_180028F1E
0x180028f06  cmp     byte ptr [rdx], 0Bh
0x180028f09  jz      short loc_180028F1E
0x180028f0b  cmp     [rdi+8], r14d
0x180028f0f  jl      short loc_180028F1E
0x180028f11  mov     dword ptr [rdi+8], 8007065Dh
0x180028f18  jmp     short loc_180028F1E
0x180028f1a  mov     byte ptr [rcx+18h], 1
0x180028f1e  mov     rdx, [rdi]
0x180028f21  mov     rax, [rdx+8]
0x180028f25  cmp     rax, [rdx+10h]
0x180028f29  jnb     short loc_180028F3C
0x180028f2b  mov     cl, [rax]
0x180028f2d  inc     rax
0x180028f30  mov     [rdx+8], rax
0x180028f34  mov     [rbx+8], cl
0x180028f37  jmp     loc_1800293AC
0x180028f3c  mov     byte ptr [rdx+18h], 1
0x180028f40  jmp     loc_1800293AC
0x180028f45  xor     eax, eax
0x180028f47  mov     [rbx+8], al
0x180028f4a  jmp     loc_1800293AC
0x180028f4f  lea     rax, aValue; "value"
0x180028f56  mov     byte ptr [rbp+arg_8], r14b
0x180028f5a  mov     rcx, rdi; this
0x180028f5d  mov     [rdi+10h], rax
0x180028f61  mov     byte ptr [rdi+18h], 5
0x180028f65  call    ?search@input_archive@tson@@AEAA_NXZ; tson::input_archive::search(void)
0x180028f6a  test    al, al
0x180028f6c  jz      short loc_180028FC6
0x180028f6e  mov     rcx, [rdi]
0x180028f71  mov     rdx, [rcx+8]
0x180028f75  cmp     rdx, [rcx+10h]
0x180028f79  jnb     short loc_180028F9C
0x180028f7b  lea     rax, [rdx+1]
0x180028f7f  mov     [rcx+8], rax
0x180028f83  test    rdx, rdx
0x180028f86  jz      short loc_180028FA0
0x180028f88  cmp     byte ptr [rdx], 0Ah
0x180028f8b  jz      short loc_180028FA0
0x180028f8d  cmp     [rdi+8], r14d
0x180028f91  jl      short loc_180028FA0
0x180028f93  mov     dword ptr [rdi+8], 8007065Dh
0x180028f9a  jmp     short loc_180028FA0
0x180028f9c  mov     byte ptr [rcx+18h], 1
0x180028fa0  mov     rdx, [rdi]
0x180028fa3  mov     rax, [rdx+8]
0x180028fa7  cmp     rax, [rdx+10h]
0x180028fab  jnb     short loc_180028FBD
0x180028fad  mov     cl, [rax]
0x180028faf  inc     rax
0x180028fb2  test    cl, cl
0x180028fb4  mov     [rdx+8], rax
0x180028fb8  setnz   al
0x180028fbb  jmp     short loc_180028FC8
0x180028fbd  mov     byte ptr [rdx+18h], 1
0x180028fc1  mov     al, byte ptr [rbp+arg_8]
0x180028fc4  jmp     short loc_180028FC8
0x180028fc6  xor     eax, eax
0x180028fc8  test    al, al
0x180028fca  jz      short loc_180028FD4
0x180028fcc  or      eax, 0FFFFFFFFh
0x180028fcf  jmp     loc_180029144
0x180028fd4  mov     eax, r14d
0x180028fd7  jmp     loc_180029144
0x180028fdc  lea     rax, aValue; "value"
0x180028fe3  mov     byte ptr [rdi+18h], 5
0x180028fe7  mov     rcx, rdi; this
0x180028fea  mov     [rdi+10h], rax
0x180028fee  call    ?search@input_archive@tson@@AEAA_NXZ; tson::input_archive::search(void)
0x180028ff3  test    al, al
0x180028ff5  jz      loc_180029338
0x180028ffb  mov     rcx, [rdi]
0x180028ffe  mov     rdx, [rcx+8]
0x180029002  cmp     rdx, [rcx+10h]
0x180029006  jnb     short loc_180029029
0x180029008  lea     rax, [rdx+1]
0x18002900c  mov     [rcx+8], rax
0x180029010  test    rdx, rdx
0x180029013  jz      short loc_18002902D
0x180029015  cmp     byte ptr [rdx], 15h
0x180029018  jz      short loc_18002902D
0x18002901a  cmp     [rdi+8], r14d
0x18002901e  jl      short loc_18002902D
0x180029020  mov     dword ptr [rdi+8], 8007065Dh
0x180029027  jmp     short loc_18002902D
0x180029029  mov     byte ptr [rcx+18h], 1
0x18002902d  mov     rcx, [rdi]
0x180029030  mov     rdx, [rcx+8]
0x180029034  lea     rax, [rdx+8]
0x180029038  cmp     rax, [rcx+10h]
0x18002903c  ja      short loc_18002904F
0x18002903e  mov     rax, [rdx]
0x180029041  mov     [rsi+18h], rax
0x180029045  add     qword ptr [rcx+8], 8
0x18002904a  jmp     loc_1800293AC
0x18002904f  mov     byte ptr [rcx+18h], 1
0x180029053  jmp     loc_1800293AC
0x180029058  lea     rax, aValue; "value"
0x18002905f  mov     byte ptr [rdi+18h], 5
0x180029063  mov     rcx, rdi; this
0x180029066  mov     [rdi+10h], rax
0x18002906a  call    ?search@input_archive@tson@@AEAA_NXZ; tson::input_archive::search(void)
0x18002906f  test    al, al
0x180029071  jz      short loc_1800290C5
0x180029073  mov     rcx, [rdi]
0x180029076  mov     rdx, [rcx+8]
0x18002907a  cmp     rdx, [rcx+10h]
0x18002907e  jnb     short loc_1800290A1
0x180029080  lea     rax, [rdx+1]
0x180029084  mov     [rcx+8], rax
0x180029088  test    rdx, rdx
0x18002908b  jz      short loc_1800290A5
0x18002908d  cmp     byte ptr [rdx], 11h
0x180029090  jz      short loc_1800290A5
0x180029092  cmp     [rdi+8], r14d
0x180029096  jl      short loc_1800290A5
0x180029098  mov     dword ptr [rdi+8], 8007065Dh
0x18002909f  jmp     short loc_1800290A5
0x1800290a1  mov     byte ptr [rcx+18h], 1
0x1800290a5  mov     rcx, [rdi]
0x1800290a8  mov     rdx, [rcx+8]
0x1800290ac  lea     rax, [rdx+4]
0x1800290b0  cmp     rax, [rcx+10h]
0x1800290b4  ja      short loc_18002904F
0x1800290b6  mov     eax, [rdx]
0x1800290b8  mov     [rsi+18h], eax
0x1800290bb  add     qword ptr [rcx+8], 4
0x1800290c0  jmp     loc_1800293AC
0x1800290c5  xor     eax, eax
0x1800290c7  mov     [rsi+18h], eax
0x1800290ca  jmp     loc_1800293AC
0x1800290cf  lea     rax, aValue; "value"
0x1800290d6  mov     byte ptr [rdi+18h], 5
0x1800290da  mov     rcx, rdi; this
0x1800290dd  mov     [rdi+10h], rax
0x1800290e1  call    ?search@input_archive@tson@@AEAA_NXZ; tson::input_archive::search(void)
0x1800290e6  test    al, al
0x1800290e8  jz      short loc_180029142
0x1800290ea  mov     rcx, [rdi]
0x1800290ed  mov     rdx, [rcx+8]
0x1800290f1  cmp     rdx, [rcx+10h]
0x1800290f5  jnb     short loc_180029118
0x1800290f7  lea     rax, [rdx+1]
0x1800290fb  mov     [rcx+8], rax
0x1800290ff  test    rdx, rdx
0x180029102  jz      short loc_18002911C
0x180029104  cmp     byte ptr [rdx], 0Dh
0x180029107  jz      short loc_18002911C
0x180029109  cmp     [rdi+8], r14d
0x18002910d  jl      short loc_18002911C
0x18002910f  mov     dword ptr [rdi+8], 8007065Dh
0x180029116  jmp     short loc_18002911C
0x180029118  mov     byte ptr [rcx+18h], 1
0x18002911c  mov     rcx, [rdi]
0x18002911f  mov     rdx, [rcx+8]
0x180029123  lea     rax, [rdx+2]
0x180029127  cmp     rax, [rcx+10h]
0x18002912b  ja      loc_18002904F
0x180029131  movzx   eax, word ptr [rdx]
0x180029134  mov     [rsi+18h], ax
0x180029138  add     qword ptr [rcx+8], 2
0x18002913d  jmp     loc_1800293AC
0x180029142  xor     eax, eax
0x180029144  mov     [rsi+18h], ax
0x180029148  jmp     loc_1800293AC
0x18002914d  lea     rax, aValue; "value"
0x180029154  mov     byte ptr [rdi+18h], 5
0x180029158  mov     rcx, rdi; this
0x18002915b  mov     [rdi+10h], rax
0x18002915f  call    ?search@input_archive@tson@@AEAA_NXZ; tson::input_archive::search(void)
0x180029164  test    al, al
0x180029166  jz      short loc_1800291BC
0x180029168  mov     rcx, [rdi]
0x18002916b  mov     rdx, [rcx+8]
0x18002916f  cmp     rdx, [rcx+10h]
0x180029173  jnb     short loc_180029196
0x180029175  lea     rax, [rdx+1]
0x180029179  mov     [rcx+8], rax
0x18002917d  test    rdx, rdx
0x180029180  jz      short loc_18002919A
0x180029182  cmp     byte ptr [rdx], 0Ch
0x180029185  jz      short loc_18002919A
0x180029187  cmp     [rdi+8], r14d
0x18002918b  jl      short loc_18002919A
0x18002918d  mov     dword ptr [rdi+8], 8007065Dh
0x180029194  jmp     short loc_18002919A
0x180029196  mov     byte ptr [rcx+18h], 1
0x18002919a  mov     rdx, [rdi]
0x18002919d  mov     rax, [rdx+8]
0x1800291a1  cmp     rax, [rdx+10h]
0x1800291a5  jnb     loc_180028F3C
0x1800291ab  mov     cl, [rax]
0x1800291ad  inc     rax
0x1800291b0  mov     [rdx+8], rax
0x1800291b4  mov     [rsi+18h], cl
0x1800291b7  jmp     loc_1800293AC
0x1800291bc  xor     eax, eax
0x1800291be  mov     [rsi+18h], al
0x1800291c1  jmp     loc_1800293AC
0x1800291c6  sub     ecx, 12h
0x1800291c9  jz      loc_180029389
0x1800291cf  sub     ecx, 1
0x1800291d2  jz      loc_180029340
0x1800291d8  sub     ecx, 1
0x1800291db  jz      loc_1800292F3
0x1800291e1  sub     ecx, 1
0x1800291e4  jz      loc_1800292AE
0x1800291ea  sub     ecx, 9
0x1800291ed  jz      loc_180029286
0x1800291f3  cmp     ecx, 1
0x1800291f6  jz      short loc_18002920E
0x1800291f8  cmp     [rdi+8], r14d
0x1800291fc  jl      loc_1800293AC
0x180029202  mov     dword ptr [rdi+8], 80070309h
0x180029209  jmp     loc_1800293AC
0x18002920e  lea     rax, aValue; "value"
0x180029215  mov     byte ptr [rdi+18h], 5
0x180029219  mov     [rdi+10h], rax
0x18002921d  lea     rdx, [rbp+var_50]; struct tson::string_tag *
0x180029221  xor     eax, eax
0x180029223  mov     [rbp+var_50], r14
0x180029227  mov     rcx, rdi; this
0x18002922a  mov     dword ptr [rbp+var_40+1], eax
0x18002922d  mov     word ptr [rbp+var_40+5], ax
0x180029231  mov     byte ptr [rbp+var_40+7], al
0x180029234  mov     [rbp+var_48], r14
0x180029238  mov     byte ptr [rbp+var_40], r14b
0x18002923c  call    ?loadValue@input_archive@tson@@QEAAXAEAUstring_tag@2@@Z; tson::input_archive::loadValue(tson::string_tag &)
0x180029241  mov     rcx, [rbp+var_48]
0x180029245  test    rcx, rcx
0x180029248  jz      short loc_18002927A
0x18002924a  add     rcx, rcx; cb
0x18002924d  call    cs:__imp_CoTaskMemAlloc
  ... truncated ...
```
