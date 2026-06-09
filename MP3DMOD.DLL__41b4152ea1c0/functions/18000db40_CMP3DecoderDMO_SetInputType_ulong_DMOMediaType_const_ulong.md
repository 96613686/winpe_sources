# CMP3DecoderDMO::SetInputType(ulong,_DMOMediaType const *,ulong)

- ea: `0x18000db40`
- end: `0x18000dcc8`
- name: `?SetInputType@CMP3DecoderDMO@@MEAAJKPEBU_DMOMediaType@@K@Z`
- size: `392`
- prototype: `__int64 __fastcall(CMP3DecoderDMO *this, int, const struct _DMOMediaType *, char)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000db40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000dc91`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000dca3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000dcb0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000dc91`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000dca3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000dcb0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000db62`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000db62`
- `msdmo!MoFreeMediaType` at `0x18000db9a`
- `msdmo!MoFreeMediaType` at `0x18000dc50`
- `msdmo!MoFreeMediaType` at `0x18000db9a`
- `msdmo!MoFreeMediaType` at `0x18000dc50`
- `msdmo!MoCopyMediaType` at `0x18000dc5d`
- `msdmo!MoCopyMediaType` at `0x18000dc5d`

## pseudocode

```c
__int64 __fastcall CMP3DecoderDMO::SetInputType(CMP3DecoderDMO *this, int a2, const struct _DMOMediaType *a3, char a4)
{
  struct _RTL_CRITICAL_SECTION *v4; // r14
  unsigned int v9; // ebx
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rax
  HRESULT v13; // eax
  __int64 v14; // rax

  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 200);
  EnterCriticalSection((LPCRITICAL_SECTION)this + 5);
  if ( a2 )
  {
    v9 = -2147220991;
LABEL_30:
    LeaveCriticalSection(v4);
    return v9;
  }
  v9 = 0;
  if ( (a4 & 2) != 0 )
  {
    if ( *((_DWORD *)this + 2) )
    {
      if ( (a4 & 1) == 0 )
      {
        *((_DWORD *)this + 2) = 0;
        MoFreeMediaType((DMO_MEDIA_TYPE *)((char *)this + 16));
      }
    }
    else
    {
      v9 = 1;
    }
    goto LABEL_30;
  }
  if ( a3 && (!*((_DWORD *)a3 + 18) || *((_QWORD *)a3 + 10)) )
  {
    v10 = *(_QWORD *)a3 - *(_QWORD *)&MEDIATYPE_Audio.Data1;
    if ( *(_QWORD *)a3 == *(_QWORD *)&MEDIATYPE_Audio.Data1 )
      v10 = *((_QWORD *)a3 + 1) - *(_QWORD *)MEDIATYPE_Audio.Data4;
    if ( !v10 )
    {
      v11 = *((_QWORD *)a3 + 2) - MEDIASUBTYPE_MP3;
      if ( !v11 )
        v11 = *((_QWORD *)a3 + 3) - *((_QWORD *)&MEDIASUBTYPE_MP3 + 1);
      if ( !v11 )
      {
        v12 = *(_QWORD *)((char *)a3 + 44) - *(_QWORD *)&FORMAT_WaveFormatEx.Data1;
        if ( !v12 )
          v12 = *(_QWORD *)((char *)a3 + 52) - *(_QWORD *)FORMAT_WaveFormatEx.Data4;
        if ( !v12 )
        {
          if ( *((_DWORD *)a3 + 18) < 0x12u )
          {
            v9 = -2147024809;
            goto LABEL_30;
          }
          if ( (unsigned __int16)(*(_WORD *)(*((_QWORD *)a3 + 10) + 2LL) - 1) <= 1u )
          {
            if ( (a4 & 1) == 0 )
            {
              if ( *((_DWORD *)this + 2) )
                MoFreeMediaType((DMO_MEDIA_TYPE *)((char *)this + 16));
              v13 = MoCopyMediaType((DMO_MEDIA_TYPE *)((char *)this + 16), (const DMO_MEDIA_TYPE *)a3);
              if ( v13 >= 0 )
              {
                *((_DWORD *)this + 2) = 1;
                *((_DWORD *)this + 190) = 0;
                v14 = *((_QWORD *)a3 + 10);
                *(_OWORD *)((char *)this + 440) = *(_OWORD *)v14;
                *((_WORD *)this + 228) = *(_WORD *)(v14 + 16);
                LeaveCriticalSection(v4);
                return 0;
              }
              v9 = v13;
            }
            goto LABEL_30;
          }
        }
      }
    }
    v9 = -2147220987;
    goto LABEL_30;
  }
  LeaveCriticalSection(v4);
  return 2147500035LL;
}

```

## disassembly

```asm
0x18000db40  push    rbx
0x18000db42  push    rbp
0x18000db43  push    rsi
0x18000db44  push    rdi
0x18000db45  push    r14
0x18000db47  push    r15
0x18000db49  sub     rsp, 28h
0x18000db4d  lea     r14, [rcx+0C8h]
0x18000db54  mov     rsi, rcx
0x18000db57  mov     rcx, r14; lpCriticalSection
0x18000db5a  mov     ebp, r9d
0x18000db5d  mov     rdi, r8
0x18000db60  mov     ebx, edx
0x18000db62  call    cs:__imp_EnterCriticalSection
0x18000db68  mov     r15d, 1
0x18000db6e  cmp     ebx, r15d
0x18000db71  jb      short loc_18000DB7D
0x18000db73  mov     ebx, 80040201h
0x18000db78  jmp     loc_18000DCA0
0x18000db7d  xor     ebx, ebx
0x18000db7f  test    bpl, 2
0x18000db83  jz      short loc_18000DBAD
0x18000db85  cmp     [rsi+8], ebx
0x18000db88  jz      short loc_18000DBA5
0x18000db8a  test    r15b, bpl
0x18000db8d  jnz     loc_18000DCA0
0x18000db93  lea     rcx, [rsi+10h]; pmt
0x18000db97  mov     [rsi+8], ebx
0x18000db9a  call    cs:__imp_MoFreeMediaType
0x18000dba0  jmp     loc_18000DCA0
0x18000dba5  mov     ebx, r15d
0x18000dba8  jmp     loc_18000DCA0
0x18000dbad  test    rdi, rdi
0x18000dbb0  jz      loc_18000DCAD
0x18000dbb6  cmp     [rdi+48h], ebx
0x18000dbb9  jbe     short loc_18000DBC5
0x18000dbbb  cmp     [rdi+50h], rbx
0x18000dbbf  jz      loc_18000DCAD
0x18000dbc5  mov     rax, [rdi]
0x18000dbc8  sub     rax, qword ptr cs:MEDIATYPE_Audio.Data1
0x18000dbcf  jnz     short loc_18000DBDC
0x18000dbd1  mov     rax, [rdi+8]
0x18000dbd5  sub     rax, qword ptr cs:MEDIATYPE_Audio.Data4
0x18000dbdc  test    rax, rax
0x18000dbdf  jnz     loc_18000DC9B
0x18000dbe5  mov     rax, [rdi+10h]
0x18000dbe9  sub     rax, qword ptr cs:MEDIASUBTYPE_MP3
0x18000dbf0  jnz     short loc_18000DBFD
0x18000dbf2  mov     rax, [rdi+18h]
0x18000dbf6  sub     rax, qword ptr cs:MEDIASUBTYPE_MP3+8
0x18000dbfd  test    rax, rax
0x18000dc00  jnz     loc_18000DC9B
0x18000dc06  mov     rax, [rdi+2Ch]
0x18000dc0a  sub     rax, qword ptr cs:FORMAT_WaveFormatEx.Data1
0x18000dc11  jnz     short loc_18000DC1E
0x18000dc13  mov     rax, [rdi+34h]
0x18000dc17  sub     rax, qword ptr cs:FORMAT_WaveFormatEx.Data4
0x18000dc1e  test    rax, rax
0x18000dc21  jnz     short loc_18000DC9B
0x18000dc23  cmp     dword ptr [rdi+48h], 12h
0x18000dc27  jnb     short loc_18000DC30
0x18000dc29  mov     ebx, 80070057h
0x18000dc2e  jmp     short loc_18000DCA0
0x18000dc30  mov     rax, [rdi+50h]
0x18000dc34  movzx   ecx, word ptr [rax+2]
0x18000dc38  sub     cx, r15w
0x18000dc3c  cmp     cx, r15w
0x18000dc40  ja      short loc_18000DC9B
0x18000dc42  test    r15b, bpl
0x18000dc45  jnz     short loc_18000DCA0
0x18000dc47  cmp     [rsi+8], ebx
0x18000dc4a  jz      short loc_18000DC56
0x18000dc4c  lea     rcx, [rsi+10h]; pmt
0x18000dc50  call    cs:__imp_MoFreeMediaType
0x18000dc56  mov     rdx, rdi; pmtSrc
0x18000dc59  lea     rcx, [rsi+10h]; pmtDest
0x18000dc5d  call    cs:__imp_MoCopyMediaType
0x18000dc63  test    eax, eax
0x18000dc65  jns     short loc_18000DC6B
0x18000dc67  mov     ebx, eax
0x18000dc69  jmp     short loc_18000DCA0
0x18000dc6b  mov     [rsi+8], r15d
0x18000dc6f  mov     rcx, r14; lpCriticalSection
0x18000dc72  mov     [rsi+2F8h], ebx
0x18000dc78  mov     rax, [rdi+50h]
0x18000dc7c  movups  xmm0, xmmword ptr [rax]
0x18000dc7f  movups  xmmword ptr [rsi+1B8h], xmm0
0x18000dc86  movzx   eax, word ptr [rax+10h]
0x18000dc8a  mov     [rsi+1C8h], ax
0x18000dc91  call    cs:__imp_LeaveCriticalSection
0x18000dc97  xor     eax, eax
0x18000dc99  jmp     short loc_18000DCBB
0x18000dc9b  mov     ebx, 80040205h
0x18000dca0  mov     rcx, r14; lpCriticalSection
0x18000dca3  call    cs:__imp_LeaveCriticalSection
0x18000dca9  mov     eax, ebx
0x18000dcab  jmp     short loc_18000DCBB
0x18000dcad  mov     rcx, r14; lpCriticalSection
0x18000dcb0  call    cs:__imp_LeaveCriticalSection
0x18000dcb6  mov     eax, 80004003h
0x18000dcbb  add     rsp, 28h
0x18000dcbf  pop     r15
0x18000dcc1  pop     r14
0x18000dcc3  pop     rdi
0x18000dcc4  pop     rsi
0x18000dcc5  pop     rbp
0x18000dcc6  pop     rbx
0x18000dcc7  retn
```
