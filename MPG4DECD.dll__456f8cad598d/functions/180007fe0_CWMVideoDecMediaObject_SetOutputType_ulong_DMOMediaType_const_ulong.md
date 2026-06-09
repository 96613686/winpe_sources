# CWMVideoDecMediaObject::SetOutputType(ulong,_DMOMediaType const *,ulong)

- ea: `0x180007fe0`
- end: `0x18000810d`
- name: `?SetOutputType@CWMVideoDecMediaObject@@UEAAJKPEBU_DMOMediaType@@K@Z`
- size: `301`
- prototype: `__int64 __fastcall(CWMVideoDecMediaObject *this, int, const struct _DMOMediaType *, char)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180002f08`
- `0x1800031f8`
- `0x180007fe0`
- `0x1800088b8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800080f8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800080f8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008002`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008002`
- `msdmo!MoCopyMediaType` at `0x1800080ce`
- `msdmo!MoCopyMediaType` at `0x1800080ce`
- `msdmo!MoFreeMediaType` at `0x180008034`
- `msdmo!MoFreeMediaType` at `0x1800080c1`
- `msdmo!MoFreeMediaType` at `0x180008034`
- `msdmo!MoFreeMediaType` at `0x1800080c1`

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
        v9 = CheckType(a3, (const struct _GUID *const *)&off_180027030, 9u);
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
0x180007fe0  push    rbx
0x180007fe2  push    rbp
0x180007fe3  push    rsi
0x180007fe4  push    rdi
0x180007fe5  push    r14
0x180007fe7  push    r15
0x180007fe9  sub     rsp, 38h
0x180007fed  lea     r15, [rcx+0C8h]
0x180007ff4  mov     rdi, rcx
0x180007ff7  mov     rcx, r15; lpCriticalSection
0x180007ffa  mov     r14d, r9d
0x180007ffd  mov     rsi, r8
0x180008000  mov     ebx, edx
0x180008002  call    cs:__imp_EnterCriticalSection
0x180008008  cmp     ebx, 1
0x18000800b  jb      short loc_180008017
0x18000800d  mov     ebx, 80040201h
0x180008012  jmp     loc_1800080E1
0x180008017  test    rsi, rsi
0x18000801a  jnz     short loc_180008049
0x18000801c  test    r14b, 2
0x180008020  jz      short loc_18000803F
0x180008022  xor     ebx, ebx
0x180008024  cmp     [rdi+0Ch], ebx
0x180008027  jz      loc_1800080E1
0x18000802d  lea     rcx, [rdi+68h]; pmt
0x180008031  mov     [rdi+0Ch], ebx
0x180008034  call    cs:__imp_MoFreeMediaType
0x18000803a  jmp     loc_1800080E1
0x18000803f  mov     ebx, 80004003h
0x180008044  jmp     loc_1800080E1
0x180008049  cmp     dword ptr [rdi+8], 0
0x18000804d  jnz     short loc_180008059
0x18000804f  mov     ebx, 80040203h
0x180008054  jmp     loc_1800080E1
0x180008059  movups  xmm0, xmmword ptr [rsi+2Ch]
0x18000805d  mov     r8d, [rsi+48h]
0x180008061  lea     rcx, [rsp+68h+Buf1]; Buf1
0x180008066  mov     rdx, [rsi+50h]
0x18000806a  movdqu  [rsp+68h+Buf1], xmm0
0x180008070  call    prvValidateMediaTypeSize
0x180008075  test    eax, eax
0x180008077  jns     short loc_180008080
0x180008079  mov     ebx, 80040205h
0x18000807e  jmp     short loc_1800080E1
0x180008080  mov     r8d, 9; unsigned int
0x180008086  lea     rdx, off_180027030; struct _GUID **
0x18000808d  mov     rcx, rsi; struct _DMOMediaType *
0x180008090  call    ?CheckType@@YAJPEBU_DMOMediaType@@PEBQEBU_GUID@@I@Z; CheckType(_DMOMediaType const *,_GUID const * const *,uint)
0x180008095  mov     ebx, eax
0x180008097  test    eax, eax
0x180008099  js      short loc_1800080E1
0x18000809b  mov     rdx, rsi; struct _DMOMediaType *
0x18000809e  lea     rcx, [rdi-30h]; this
0x1800080a2  call    ?CheckOutputType@CWMVideoDecMediaObject@@IEAAJPEBU_DMOMediaType@@H@Z; CWMVideoDecMediaObject::CheckOutputType(_DMOMediaType const *,int)
0x1800080a7  mov     ebx, eax
0x1800080a9  test    eax, eax
0x1800080ab  js      short loc_1800080E1
0x1800080ad  test    r14b, 1
0x1800080b1  jz      short loc_1800080B7
0x1800080b3  xor     ebx, ebx
0x1800080b5  jmp     short loc_1800080E1
0x1800080b7  cmp     dword ptr [rdi+0Ch], 0
0x1800080bb  jz      short loc_1800080C7
0x1800080bd  lea     rcx, [rdi+68h]; pmt
0x1800080c1  call    cs:__imp_MoFreeMediaType
0x1800080c7  mov     rdx, rsi; pmtSrc
0x1800080ca  lea     rcx, [rdi+68h]; pmtDest
0x1800080ce  call    cs:__imp_MoCopyMediaType
0x1800080d4  mov     ebx, eax
0x1800080d6  test    eax, eax
0x1800080d8  js      short loc_1800080E1
0x1800080da  mov     dword ptr [rdi+0Ch], 1
0x1800080e1  mov     rcx, r15; lpCriticalSection
0x1800080e4  mov     dword ptr [rdi+3BCh], 0
0x1800080ee  mov     dword ptr [rdi+5F0h], 0
0x1800080f8  call    cs:__imp_LeaveCriticalSection
0x1800080fe  mov     eax, ebx
0x180008100  add     rsp, 38h
0x180008104  pop     r15
0x180008106  pop     r14
0x180008108  pop     rdi
0x180008109  pop     rsi
0x18000810a  pop     rbp
0x18000810b  pop     rbx
0x18000810c  retn
```
