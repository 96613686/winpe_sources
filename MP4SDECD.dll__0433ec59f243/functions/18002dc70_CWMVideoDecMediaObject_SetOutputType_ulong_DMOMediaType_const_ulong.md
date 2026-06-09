# CWMVideoDecMediaObject::SetOutputType(ulong,_DMOMediaType const *,ulong)

- ea: `0x18002dc70`
- end: `0x18002deb8`
- name: `?SetOutputType@CWMVideoDecMediaObject@@UEAAJKPEBU_DMOMediaType@@K@Z`
- size: `584`
- prototype: `__int64 __fastcall(CWMVideoDecMediaObject *this, int, const struct _DMOMediaType *, char)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x18001470c`
- `0x18002bc14`
- `0x18002bfac`
- `0x18002c0bc`
- `0x18002dc70`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002dc92`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002dc92`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002dea3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002dea3`
- `msdmo!MoCopyMediaType` at `0x18002dd6d`
- `msdmo!MoCopyMediaType` at `0x18002dd6d`
- `msdmo!MoFreeMediaType` at `0x18002dcc4`
- `msdmo!MoFreeMediaType` at `0x18002dd60`
- `msdmo!MoFreeMediaType` at `0x18002dcc4`
- `msdmo!MoFreeMediaType` at `0x18002dd60`

## pseudocode

```c
__int64 __fastcall CWMVideoDecMediaObject::SetOutputType(
        CWMVideoDecMediaObject *this,
        int a2,
        const struct _DMOMediaType *a3,
        char a4)
{
  struct _RTL_CRITICAL_SECTION *v4; // r15
  HRESULT v9; // ebx
  int v10; // r8d
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rdx
  __int64 v15; // r9
  __int64 v16; // r10
  __int64 v17; // r8
  __int64 v18; // rax
  __int64 v19; // rcx
  int v20; // eax
  bool v21; // cc
  int v22; // eax
  _OWORD Buf1[4]; // [rsp+20h] [rbp-48h] BYREF

  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 216);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 216));
  if ( a2 )
  {
    v9 = -2147220991;
    goto LABEL_44;
  }
  if ( !a3 )
  {
    if ( (a4 & 2) != 0 )
    {
      v9 = 0;
      if ( *((_DWORD *)this + 3) )
      {
        *((_DWORD *)this + 3) = 0;
        MoFreeMediaType((DMO_MEDIA_TYPE *)((char *)this + 104));
      }
    }
    else
    {
      v9 = -2147467261;
    }
    goto LABEL_44;
  }
  if ( !*((_DWORD *)this + 2) )
  {
    v9 = -2147220989;
    goto LABEL_44;
  }
  Buf1[0] = *(_OWORD *)((char *)a3 + 44);
  if ( (int)prvValidateMediaTypeSize(Buf1) < 0 )
  {
    v9 = -2147220987;
    goto LABEL_44;
  }
  v9 = CheckType(a3, *((const struct _GUID *const **)this + 157), *((_DWORD *)this + 316));
  if ( v9 >= 0 )
  {
    v9 = CWMVideoDecMediaObject::CheckOutputType((CWMVideoDecMediaObject *)((char *)this - 48), a3, v10);
    if ( v9 >= 0 )
    {
      if ( (a4 & 1) != 0 )
      {
        v9 = 0;
        goto LABEL_44;
      }
      if ( *((_DWORD *)this + 3) )
        MoFreeMediaType((DMO_MEDIA_TYPE *)((char *)this + 104));
      v9 = MoCopyMediaType((DMO_MEDIA_TYPE *)((char *)this + 104), (const DMO_MEDIA_TYPE *)a3);
      if ( v9 >= 0 )
      {
        v9 = ConvertDMOMediaTypeToMFMediaType((struct _MFVIDEOFORMAT *)((char *)this + 1624), a3);
        if ( v9 >= 0 )
        {
          v11 = *(_QWORD *)&FORMAT_MFVideoFormat.Data1 - *(_QWORD *)((char *)this + 148);
          if ( *(_QWORD *)&FORMAT_MFVideoFormat.Data1 == *(_QWORD *)((char *)this + 148) )
            v11 = *(_QWORD *)FORMAT_MFVideoFormat.Data4 - *(_QWORD *)((char *)this + 156);
          if ( !v11 )
            goto LABEL_43;
          v12 = *(_QWORD *)&FORMAT_VideoInfo.Data1 - *(_QWORD *)((char *)this + 148);
          if ( *(_QWORD *)&FORMAT_VideoInfo.Data1 == *(_QWORD *)((char *)this + 148) )
            v12 = *(_QWORD *)FORMAT_VideoInfo.Data4 - *(_QWORD *)((char *)this + 156);
          if ( v12 )
          {
            v18 = *(_QWORD *)&FORMAT_VideoInfo2.Data1 - *(_QWORD *)((char *)this + 148);
            if ( *(_QWORD *)&FORMAT_VideoInfo2.Data1 == *(_QWORD *)((char *)this + 148) )
              v18 = *(_QWORD *)FORMAT_VideoInfo2.Data4 - *(_QWORD *)((char *)this + 156);
            if ( v18 )
            {
              v19 = 0;
              v14 = 8;
              v17 = 8;
              v15 = 4;
              v16 = 16;
LABEL_33:
              v20 = -*(_DWORD *)v15;
              if ( *(int *)v15 > 0 )
                v20 = *(_DWORD *)v15;
              v21 = *(_DWORD *)v16 <= 3u;
              *(_DWORD *)v15 = v20;
              if ( v21 )
              {
                v14 = v17;
              }
              else
              {
                v22 = -*(_DWORD *)v14;
                if ( *(int *)v14 > 0 )
                  v22 = *(_DWORD *)v14;
                *(_DWORD *)v14 = v22;
              }
              *((_DWORD *)this + 128) = *(_DWORD *)v14;
              if ( *(_DWORD *)(v19 + 4) >= *(_DWORD *)(v19 + 12) || *(_DWORD *)v19 >= *(_DWORD *)(v19 + 8) )
              {
                *(_QWORD *)(v19 + 8) = 0;
                *(_QWORD *)v19 = 0;
              }
LABEL_43:
              *((_DWORD *)this + 3) = 1;
              *((_DWORD *)this + 136) = 0;
              goto LABEL_44;
            }
            v13 = *((_QWORD *)this + 23);
            v14 = v13 + 80;
            v15 = v13 + 76;
            v16 = v13 + 88;
            v17 = v13 + 80;
          }
          else
          {
            v13 = *((_QWORD *)this + 23);
            v14 = v13 + 56;
            v15 = v13 + 52;
            v16 = v13 + 64;
            v17 = v13 + 56;
          }
          v19 = v13 + 16;
          goto LABEL_33;
        }
      }
    }
  }
LABEL_44:
  LeaveCriticalSection(v4);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18002dc70  push    rbx
0x18002dc72  push    rbp
0x18002dc73  push    rsi
0x18002dc74  push    rdi
0x18002dc75  push    r14
0x18002dc77  push    r15
0x18002dc79  sub     rsp, 38h
0x18002dc7d  lea     r15, [rcx+0D8h]
0x18002dc84  mov     rdi, rcx
0x18002dc87  mov     rcx, r15; lpCriticalSection
0x18002dc8a  mov     r14d, r9d
0x18002dc8d  mov     rsi, r8
0x18002dc90  mov     ebx, edx
0x18002dc92  call    cs:__imp_EnterCriticalSection
0x18002dc98  cmp     ebx, 1
0x18002dc9b  jb      short loc_18002DCA7
0x18002dc9d  mov     ebx, 80040201h
0x18002dca2  jmp     loc_18002DEA0
0x18002dca7  test    rsi, rsi
0x18002dcaa  jnz     short loc_18002DCD9
0x18002dcac  test    r14b, 2
0x18002dcb0  jz      short loc_18002DCCF
0x18002dcb2  xor     ebx, ebx
0x18002dcb4  cmp     [rdi+0Ch], ebx
0x18002dcb7  jz      loc_18002DEA0
0x18002dcbd  lea     rcx, [rdi+68h]; pmt
0x18002dcc1  mov     [rdi+0Ch], ebx
0x18002dcc4  call    cs:__imp_MoFreeMediaType
0x18002dcca  jmp     loc_18002DEA0
0x18002dccf  mov     ebx, 80004003h
0x18002dcd4  jmp     loc_18002DEA0
0x18002dcd9  cmp     dword ptr [rdi+8], 0
0x18002dcdd  jnz     short loc_18002DCE9
0x18002dcdf  mov     ebx, 80040203h
0x18002dce4  jmp     loc_18002DEA0
0x18002dce9  movups  xmm0, xmmword ptr [rsi+2Ch]
0x18002dced  mov     r8d, [rsi+48h]
0x18002dcf1  lea     rcx, [rsp+68h+Buf1]; Buf1
0x18002dcf6  mov     rdx, [rsi+50h]
0x18002dcfa  movdqu  [rsp+68h+Buf1], xmm0
0x18002dd00  call    prvValidateMediaTypeSize
0x18002dd05  test    eax, eax
0x18002dd07  jns     short loc_18002DD13
0x18002dd09  mov     ebx, 80040205h
0x18002dd0e  jmp     loc_18002DEA0
0x18002dd13  mov     r8d, [rdi+4F0h]; unsigned int
0x18002dd1a  mov     rcx, rsi; struct _DMOMediaType *
0x18002dd1d  mov     rdx, [rdi+4E8h]; struct _GUID **
0x18002dd24  call    ?CheckType@@YAJPEBU_DMOMediaType@@PEBQEBU_GUID@@I@Z; CheckType(_DMOMediaType const *,_GUID const * const *,uint)
0x18002dd29  mov     ebx, eax
0x18002dd2b  test    eax, eax
0x18002dd2d  js      loc_18002DEA0
0x18002dd33  mov     rdx, rsi; struct _DMOMediaType *
0x18002dd36  lea     rcx, [rdi-30h]; this
0x18002dd3a  call    ?CheckOutputType@CWMVideoDecMediaObject@@AEAAJPEBU_DMOMediaType@@H@Z; CWMVideoDecMediaObject::CheckOutputType(_DMOMediaType const *,int)
0x18002dd3f  mov     ebx, eax
0x18002dd41  test    eax, eax
0x18002dd43  js      loc_18002DEA0
0x18002dd49  test    r14b, 1
0x18002dd4d  jz      short loc_18002DD56
0x18002dd4f  xor     ebx, ebx
0x18002dd51  jmp     loc_18002DEA0
0x18002dd56  cmp     dword ptr [rdi+0Ch], 0
0x18002dd5a  jz      short loc_18002DD66
0x18002dd5c  lea     rcx, [rdi+68h]; pmt
0x18002dd60  call    cs:__imp_MoFreeMediaType
0x18002dd66  mov     rdx, rsi; pmtSrc
0x18002dd69  lea     rcx, [rdi+68h]; pmtDest
0x18002dd6d  call    cs:__imp_MoCopyMediaType
0x18002dd73  mov     ebx, eax
0x18002dd75  test    eax, eax
0x18002dd77  js      loc_18002DEA0
0x18002dd7d  lea     rcx, [rdi+658h]; struct _MFVIDEOFORMAT *
0x18002dd84  mov     rdx, rsi; struct _DMOMediaType *
0x18002dd87  call    ?ConvertDMOMediaTypeToMFMediaType@@YAJPEAU_MFVIDEOFORMAT@@PEBU_DMOMediaType@@@Z; ConvertDMOMediaTypeToMFMediaType(_MFVIDEOFORMAT *,_DMOMediaType const *)
0x18002dd8c  mov     ebx, eax
0x18002dd8e  test    eax, eax
0x18002dd90  js      loc_18002DEA0
0x18002dd96  mov     rax, qword ptr cs:FORMAT_MFVideoFormat.Data1
0x18002dd9d  sub     rax, [rdi+94h]
0x18002dda4  jnz     short loc_18002DDB4
0x18002dda6  mov     rax, qword ptr cs:FORMAT_MFVideoFormat.Data4
0x18002ddad  sub     rax, [rdi+9Ch]
0x18002ddb4  test    rax, rax
0x18002ddb7  jz      loc_18002DE8F
0x18002ddbd  mov     rax, qword ptr cs:FORMAT_VideoInfo.Data1
0x18002ddc4  sub     rax, [rdi+94h]
0x18002ddcb  jnz     short loc_18002DDDB
0x18002ddcd  mov     rax, qword ptr cs:FORMAT_VideoInfo.Data4
0x18002ddd4  sub     rax, [rdi+9Ch]
0x18002dddb  test    rax, rax
0x18002ddde  jnz     short loc_18002DDF9
0x18002dde0  mov     rax, [rdi+0B8h]
0x18002dde7  lea     rdx, [rax+38h]
0x18002ddeb  lea     r9, [rax+34h]
0x18002ddef  lea     r10, [rax+40h]
0x18002ddf3  lea     r8, [rax+38h]
0x18002ddf7  jmp     short loc_18002DE45
0x18002ddf9  mov     rax, qword ptr cs:FORMAT_VideoInfo2.Data1
0x18002de00  sub     rax, [rdi+94h]
0x18002de07  jnz     short loc_18002DE17
0x18002de09  mov     rax, qword ptr cs:FORMAT_VideoInfo2.Data4
0x18002de10  sub     rax, [rdi+9Ch]
0x18002de17  test    rax, rax
0x18002de1a  jz      short loc_18002DE2E
0x18002de1c  xor     ecx, ecx
0x18002de1e  lea     edx, [rcx+8]
0x18002de21  mov     r8d, edx
0x18002de24  lea     r9d, [rcx+4]
0x18002de28  lea     r10d, [rcx+10h]
0x18002de2c  jmp     short loc_18002DE49
0x18002de2e  mov     rax, [rdi+0B8h]
0x18002de35  lea     rdx, [rax+50h]
0x18002de39  lea     r9, [rax+4Ch]
0x18002de3d  lea     r10, [rax+58h]
0x18002de41  lea     r8, [rax+50h]
0x18002de45  lea     rcx, [rax+10h]
0x18002de49  mov     eax, [r9]
0x18002de4c  neg     eax
0x18002de4e  cmovs   eax, [r9]
0x18002de52  cmp     dword ptr [r10], 3
0x18002de56  mov     [r9], eax
0x18002de59  jbe     short loc_18002DE66
0x18002de5b  mov     eax, [rdx]
0x18002de5d  neg     eax
0x18002de5f  cmovs   eax, [rdx]
0x18002de62  mov     [rdx], eax
0x18002de64  jmp     short loc_18002DE69
0x18002de66  mov     rdx, r8
0x18002de69  mov     eax, [rdx]
0x18002de6b  mov     [rdi+200h], eax
0x18002de71  mov     eax, [rcx+0Ch]
0x18002de74  cmp     [rcx+4], eax
0x18002de77  jge     short loc_18002DE80
0x18002de79  mov     eax, [rcx+8]
0x18002de7c  cmp     [rcx], eax
0x18002de7e  jl      short loc_18002DE8F
0x18002de80  mov     qword ptr [rcx+8], 0
0x18002de88  mov     qword ptr [rcx], 0
0x18002de8f  mov     dword ptr [rdi+0Ch], 1
0x18002de96  mov     dword ptr [rdi+220h], 0
0x18002dea0  mov     rcx, r15; lpCriticalSection
0x18002dea3  call    cs:__imp_LeaveCriticalSection
0x18002dea9  mov     eax, ebx
0x18002deab  add     rsp, 38h
0x18002deaf  pop     r15
0x18002deb1  pop     r14
0x18002deb3  pop     rdi
0x18002deb4  pop     rsi
0x18002deb5  pop     rbp
0x18002deb6  pop     rbx
0x18002deb7  retn
```
