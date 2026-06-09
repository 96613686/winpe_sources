# CWMVideoDecMediaObject::SetOutputType(ulong,_DMOMediaType const *,ulong)

- ea: `0x180007f20`
- end: `0x18000804d`
- name: `?SetOutputType@CWMVideoDecMediaObject@@UEAAJKPEBU_DMOMediaType@@K@Z`
- size: `301`
- prototype: `int(CWMVideoDecMediaObject *__hidden this, unsigned int, const struct _DMOMediaType *, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180002e48`
- `0x180003138`
- `0x180007f20`
- `0x1800087f8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008038`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008038`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007f42`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007f42`
- `msdmo!MoCopyMediaType` at `0x18000800e`
- `msdmo!MoCopyMediaType` at `0x18000800e`
- `msdmo!MoFreeMediaType` at `0x180007f74`
- `msdmo!MoFreeMediaType` at `0x180008001`
- `msdmo!MoFreeMediaType` at `0x180007f74`
- `msdmo!MoFreeMediaType` at `0x180008001`

## pseudocode

```c
__int64 __fastcall CWMVideoDecMediaObject::SetOutputType(
        CWMVideoDecMediaObject *this,
        int a2,
        const struct _DMOMediaType *a3,
        char a4)
{
  struct _RTL_CRITICAL_SECTION *v4; // r15
  int v9; // ebx
  LONG v10; // r8d
  _OWORD Buf1[4]; // [rsp+20h] [rbp-48h] BYREF

  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 200);
  EnterCriticalSection((LPCRITICAL_SECTION)this + 5);
  if ( a2 )
  {
    v9 = -2147220991;
  }
  else if ( a3 )
  {
    if ( *((_DWORD *)this + 2) )
    {
      Buf1[0] = *(_OWORD *)((char *)a3 + 44);
      if ( (int)prvValidateMediaTypeSize(Buf1) >= 0 )
      {
        v9 = CheckType(a3, (const struct _GUID *const *)&off_180027020, 9u);
        if ( v9 >= 0 )
        {
          v9 = CWMVideoDecMediaObject::CheckOutputType((CWMVideoDecMediaObject *)((char *)this - 48), a3, v10);
          if ( v9 >= 0 )
          {
            if ( (a4 & 1) != 0 )
            {
              v9 = 0;
            }
            else
            {
              if ( *((_DWORD *)this + 3) )
                MoFreeMediaType((DMO_MEDIA_TYPE *)((char *)this + 104));
              v9 = MoCopyMediaType((DMO_MEDIA_TYPE *)((char *)this + 104), (const DMO_MEDIA_TYPE *)a3);
              if ( v9 >= 0 )
                *((_DWORD *)this + 3) = 1;
            }
          }
        }
      }
      else
      {
        v9 = -2147220987;
      }
    }
    else
    {
      v9 = -2147220989;
    }
  }
  else if ( (a4 & 2) != 0 )
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
  *((_DWORD *)this + 239) = 0;
  *((_DWORD *)this + 380) = 0;
  LeaveCriticalSection(v4);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180007f20  push    rbx
0x180007f22  push    rbp
0x180007f23  push    rsi
0x180007f24  push    rdi
0x180007f25  push    r14
0x180007f27  push    r15
0x180007f29  sub     rsp, 38h
0x180007f2d  lea     r15, [rcx+0C8h]
0x180007f34  mov     rdi, rcx
0x180007f37  mov     rcx, r15; lpCriticalSection
0x180007f3a  mov     r14d, r9d
0x180007f3d  mov     rsi, r8
0x180007f40  mov     ebx, edx
0x180007f42  call    cs:__imp_EnterCriticalSection
0x180007f48  cmp     ebx, 1
0x180007f4b  jb      short loc_180007F57
0x180007f4d  mov     ebx, 80040201h
0x180007f52  jmp     loc_180008021
0x180007f57  test    rsi, rsi
0x180007f5a  jnz     short loc_180007F89
0x180007f5c  test    r14b, 2
0x180007f60  jz      short loc_180007F7F
0x180007f62  xor     ebx, ebx
0x180007f64  cmp     [rdi+0Ch], ebx
0x180007f67  jz      loc_180008021
0x180007f6d  lea     rcx, [rdi+68h]; pmt
0x180007f71  mov     [rdi+0Ch], ebx
0x180007f74  call    cs:__imp_MoFreeMediaType
0x180007f7a  jmp     loc_180008021
0x180007f7f  mov     ebx, 80004003h
0x180007f84  jmp     loc_180008021
0x180007f89  cmp     dword ptr [rdi+8], 0
0x180007f8d  jnz     short loc_180007F99
0x180007f8f  mov     ebx, 80040203h
0x180007f94  jmp     loc_180008021
0x180007f99  movups  xmm0, xmmword ptr [rsi+2Ch]
0x180007f9d  mov     r8d, [rsi+48h]
0x180007fa1  lea     rcx, [rsp+68h+Buf1]; Buf1
0x180007fa6  mov     rdx, [rsi+50h]
0x180007faa  movdqu  [rsp+68h+Buf1], xmm0
0x180007fb0  call    prvValidateMediaTypeSize
0x180007fb5  test    eax, eax
0x180007fb7  jns     short loc_180007FC0
0x180007fb9  mov     ebx, 80040205h
0x180007fbe  jmp     short loc_180008021
0x180007fc0  mov     r8d, 9; unsigned int
0x180007fc6  lea     rdx, off_180027020; struct _GUID **
0x180007fcd  mov     rcx, rsi; struct _DMOMediaType *
0x180007fd0  call    ?CheckType@@YAJPEBU_DMOMediaType@@PEBQEBU_GUID@@I@Z; CheckType(_DMOMediaType const *,_GUID const * const *,uint)
0x180007fd5  mov     ebx, eax
0x180007fd7  test    eax, eax
0x180007fd9  js      short loc_180008021
0x180007fdb  mov     rdx, rsi; struct _DMOMediaType *
0x180007fde  lea     rcx, [rdi-30h]; this
0x180007fe2  call    ?CheckOutputType@CWMVideoDecMediaObject@@IEAAJPEBU_DMOMediaType@@H@Z; CWMVideoDecMediaObject::CheckOutputType(_DMOMediaType const *,int)
0x180007fe7  mov     ebx, eax
0x180007fe9  test    eax, eax
0x180007feb  js      short loc_180008021
0x180007fed  test    r14b, 1
0x180007ff1  jz      short loc_180007FF7
0x180007ff3  xor     ebx, ebx
0x180007ff5  jmp     short loc_180008021
0x180007ff7  cmp     dword ptr [rdi+0Ch], 0
0x180007ffb  jz      short loc_180008007
0x180007ffd  lea     rcx, [rdi+68h]; pmt
0x180008001  call    cs:__imp_MoFreeMediaType
0x180008007  mov     rdx, rsi; pmtSrc
0x18000800a  lea     rcx, [rdi+68h]; pmtDest
0x18000800e  call    cs:__imp_MoCopyMediaType
0x180008014  mov     ebx, eax
0x180008016  test    eax, eax
0x180008018  js      short loc_180008021
0x18000801a  mov     dword ptr [rdi+0Ch], 1
0x180008021  mov     rcx, r15; lpCriticalSection
0x180008024  mov     dword ptr [rdi+3BCh], 0
0x18000802e  mov     dword ptr [rdi+5F0h], 0
0x180008038  call    cs:__imp_LeaveCriticalSection
0x18000803e  mov     eax, ebx
0x180008040  add     rsp, 38h
0x180008044  pop     r15
0x180008046  pop     r14
0x180008048  pop     rdi
0x180008049  pop     rsi
0x18000804a  pop     rbp
0x18000804b  pop     rbx
0x18000804c  retn
```
