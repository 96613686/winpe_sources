# EquationManager::CommitEquationStatesToDevice(unsigned __int64)

- ea: `0x180011c7c`
- end: `0x180011f41`
- name: `?CommitEquationStatesToDevice@EquationManager@@AEAAJ_K@Z`
- size: `709`
- prototype: `__int64 __fastcall(EquationManager *__hidden this, unsigned __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001f4d0`

## callees

- `0x180001304`
- `0x18000c11c`
- `0x18000d68c`
- `0x18000f588`
- `0x180011c7c`
- `0x18001be98`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011e73`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011f12`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011e73`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011f12`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011ca1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011ca1`

## pseudocode

```c
__int64 __fastcall EquationManager::CommitEquationStatesToDevice(EquationManager *this, __int64 a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbx
  unsigned __int8 i; // r9
  __int64 v6; // r11
  __int64 v7; // rdx
  unsigned __int64 v8; // r10
  unsigned int v9; // r8d
  unsigned int v10; // r8d
  int v11; // eax
  _BYTE *v12; // r11
  unsigned __int8 j; // cl
  unsigned __int64 v14; // rax
  unsigned __int8 k; // r10
  __int64 v16; // r8
  unsigned __int64 v17; // rdx
  char v18; // al
  const struct std::nothrow_t *v19; // rdx
  int v20; // edi
  __int64 v21; // r8
  __int64 v22; // r9
  __int64 m; // rdx
  __int64 v25; // rcx
  int v26; // r8d
  __int64 v27; // r10
  unsigned __int64 v28; // r9
  unsigned __int64 v29; // rax
  int v30; // [rsp+40h] [rbp-49h] BYREF
  int v31; // [rsp+44h] [rbp-45h] BYREF
  const char *v32; // [rsp+48h] [rbp-41h] BYREF
  PVOID P[18]; // [rsp+50h] [rbp-39h] BYREF

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 4408);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 4408));
  for ( i = 0; i < 0x10u; ++i )
  {
    v6 = i;
    v7 = *((_QWORD *)this + 2 * i + 518);
    if ( v7 )
    {
      v8 = *(_QWORD *)(v7 + 72) >> 3;
      v9 = *(_BYTE *)(v7 + 72) & 7 | 0xFFFFFFF8;
      if ( (*(_BYTE *)(v7 + 72) & 4) == 0 )
        v9 = *(_DWORD *)(v7 + 72) & 7;
      if ( v9 )
      {
        v10 = v9 - 1;
        if ( v10 )
        {
          if ( v10 != 1 )
          {
            GameInputFailFast(2147549183LL, 105);
            JUMPOUT(0x180011F40LL);
          }
          if ( v8 > *(_QWORD *)(v7 + 80) )
          {
            if ( *(_DWORD *)(v7 + 88) != 2 )
            {
              v11 = 2;
              goto LABEL_25;
            }
LABEL_13:
            v11 = 15;
            goto LABEL_25;
          }
          if ( *(_DWORD *)(v7 + 88) != 1 && *(_DWORD *)(v7 + 88) != 4 )
            goto LABEL_13;
          v11 = 3;
        }
        else if ( v8 > *(_QWORD *)(v7 + 80) || *(_DWORD *)(v7 + 88) == 2 )
        {
          v11 = 1;
        }
        else
        {
          v11 = 15;
          if ( *(_DWORD *)(v7 + 88) == 3 )
            v11 = 4;
        }
      }
      else
      {
        v11 = 15;
        if ( *(_DWORD *)(v7 + 88) != 2 )
          v11 = 2;
      }
    }
    else
    {
      v11 = 0;
    }
LABEL_25:
    *((_DWORD *)&P[4] + v6) = v11;
  }
  UsbGipRequest::UsbGipRequest((UsbGipRequest *)P, 9u, 0xCu);
  v12 = P[0];
  for ( j = 0; j < 0x10u; j += 2 )
  {
    v14 = j;
    v12[(v14 >> 1) + 20] = -1;
  }
  for ( k = 0; k < 0x10u; ++k )
  {
    v16 = k;
    v17 = k;
    v18 = 4 * ((k & 1) == 0);
    v12[(v17 >> 1) + 20] = v12[(v17 >> 1) + 20] & ~(15 << v18) | (15 << v18) & (*((_BYTE *)&P[4] + 4 * v16) << v18);
  }
  v20 = EquationManager::SendRequest(this, (const struct UsbGipRequest *)P);
  if ( v20 >= 0 )
  {
    for ( m = 0; m != 16; ++m )
    {
      v25 = *((_QWORD *)this + 2 * m + 518);
      if ( v25 )
      {
        v26 = *((_DWORD *)&P[4] + m);
        if ( v26 != 15 )
        {
          v27 = *((_QWORD *)this + 560);
          if ( v26 == 1 )
          {
            *(_QWORD *)(v25 + 104) = *(_QWORD *)(v25 + 64);
          }
          else if ( v26 == 3 && *(_QWORD *)(v25 + 64) != -1 )
          {
            v28 = *(_QWORD *)(v25 + 104);
            v29 = a2 - *(_QWORD *)(v25 + 80);
            if ( v29 < v28 )
              *(_QWORD *)(v25 + 104) = v28 - v29;
            else
              *(_QWORD *)(v25 + 104) = 0;
          }
          *(_QWORD *)(v25 + 80) = a2;
          *(_DWORD *)(v25 + 88) = v26;
          *(_QWORD *)(v25 + 96) = v27;
        }
      }
    }
    if ( P[0] != (PVOID)-1LL )
      operator delete(P[0], (const struct std::nothrow_t *)0x10);
    LeaveCriticalSection(v2);
    return 0;
  }
  else
  {
    if ( (unsigned int)dword_180069000 > 2 )
    {
      v19 = (const struct std::nothrow_t *)qword_180069018;
      if ( (qword_180069010 & 8) != 0 && (qword_180069018 & 8) == qword_180069018 )
      {
        v30 = v20;
        v32 = "onecore\\xbox\\gameinput\\feedback\\gipequationmanager\\EquationManager.cpp";
        v31 = 332;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          qword_180069010,
          (unsigned __int8 *)word_18005BF82,
          v21,
          v22,
          (__int64 **)&v32,
          (__int64)&v31,
          (__int64)&v30);
      }
    }
    if ( P[0] != (PVOID)-1LL )
      operator delete(P[0], v19);
    LeaveCriticalSection(v2);
    return (unsigned int)v20;
  }
}

```

## disassembly

```asm
0x180011c7c  push    rbp
0x180011c7e  push    rbx
0x180011c7f  push    rsi
0x180011c80  push    rdi
0x180011c81  push    r14
0x180011c83  push    r15
0x180011c85  lea     rbp, [rsp-2Fh]
0x180011c8a  sub     rsp, 0B8h
0x180011c91  lea     rbx, [rcx+1138h]
0x180011c98  mov     rsi, rcx
0x180011c9b  mov     rcx, rbx; lpCriticalSection
0x180011c9e  mov     r14, rdx
0x180011ca1  call    cs:__imp_EnterCriticalSection
0x180011ca8  nop     dword ptr [rax+rax+00h]
0x180011cad  mov     edi, 4
0x180011cb2  xor     r9b, r9b
0x180011cb5  lea     r15d, [rdi-2]
0x180011cb9  movzx   r11d, r9b
0x180011cbd  lea     rax, [r11+103h]
0x180011cc4  add     rax, rax
0x180011cc7  mov     rdx, [rsi+rax*8]
0x180011ccb  test    rdx, rdx
0x180011cce  jz      loc_180011D61
0x180011cd4  mov     rcx, [rdx+48h]
0x180011cd8  mov     r10, [rdx+48h]
0x180011cdc  and     ecx, 7
0x180011cdf  shr     r10, 3
0x180011ce3  mov     r8d, ecx
0x180011ce6  or      r8d, 0FFFFFFF8h
0x180011cea  test    [rdx+48h], dil
0x180011cee  cmovz   r8d, ecx
0x180011cf2  test    r8d, r8d
0x180011cf5  jz      short loc_180011D52
0x180011cf7  sub     r8d, 1
0x180011cfb  jz      short loc_180011D31
0x180011cfd  cmp     r8d, 1
0x180011d01  jnz     loc_180011F31
0x180011d07  cmp     r10, [rdx+50h]
0x180011d0b  jbe     short loc_180011D18
0x180011d0d  cmp     [rdx+58h], r15d
0x180011d11  jz      short loc_180011D23
0x180011d13  mov     eax, r15d
0x180011d16  jmp     short loc_180011D63
0x180011d18  cmp     dword ptr [rdx+58h], 1
0x180011d1c  jz      short loc_180011D2A
0x180011d1e  cmp     [rdx+58h], edi
0x180011d21  jz      short loc_180011D2A
0x180011d23  mov     eax, 0Fh
0x180011d28  jmp     short loc_180011D63
0x180011d2a  mov     eax, 3
0x180011d2f  jmp     short loc_180011D63
0x180011d31  cmp     r10, [rdx+50h]
0x180011d35  ja      short loc_180011D4B
0x180011d37  cmp     [rdx+58h], r15d
0x180011d3b  jz      short loc_180011D4B
0x180011d3d  cmp     dword ptr [rdx+58h], 3
0x180011d41  mov     eax, 0Fh
0x180011d46  cmovz   eax, edi
0x180011d49  jmp     short loc_180011D63
0x180011d4b  mov     eax, 1
0x180011d50  jmp     short loc_180011D63
0x180011d52  cmp     [rdx+58h], r15d
0x180011d56  mov     eax, 0Fh
0x180011d5b  cmovnz  eax, r15d
0x180011d5f  jmp     short loc_180011D63
0x180011d61  xor     eax, eax
0x180011d63  inc     r9b
0x180011d66  mov     [rbp+r11*4+57h+var_70], eax
0x180011d6b  cmp     r9b, 10h
0x180011d6f  jb      loc_180011CB9
0x180011d75  mov     r8b, 0Ch; unsigned __int8
0x180011d78  lea     rcx, [rbp+57h+P]; this
0x180011d7c  mov     edx, 9; unsigned int
0x180011d81  call    ??0UsbGipRequest@@QEAA@IE@Z; UsbGipRequest::UsbGipRequest(uint,uchar)
0x180011d86  mov     r11, [rbp+57h+P]
0x180011d8a  xor     cl, cl
0x180011d8c  movzx   eax, cl
0x180011d8f  add     cl, r15b
0x180011d92  shr     rax, 1
0x180011d95  mov     byte ptr [rax+r11+14h], 0FFh
0x180011d9b  cmp     cl, 10h
0x180011d9e  jb      short loc_180011D8C
0x180011da0  xor     r10b, r10b
0x180011da3  movzx   r8d, r10b
0x180011da7  mov     al, r10b
0x180011daa  not     al
0x180011dac  mov     r9d, 0Fh
0x180011db2  and     al, 1
0x180011db4  mov     edx, r8d
0x180011db7  shl     al, 2
0x180011dba  inc     r10b
0x180011dbd  movzx   ecx, al
0x180011dc0  mov     al, byte ptr [rbp+r8*4+57h+var_70]
0x180011dc5  shl     r9b, cl
0x180011dc8  shl     al, cl
0x180011dca  and     al, r9b
0x180011dcd  shr     rdx, 1
0x180011dd0  not     r9b
0x180011dd3  and     r9b, [rdx+r11+14h]
0x180011dd8  or      al, r9b
0x180011ddb  mov     [rdx+r11+14h], al
0x180011de0  cmp     r10b, 10h
0x180011de4  jb      short loc_180011DA3
0x180011de6  lea     rdx, [rbp+57h+P]; struct UsbGipRequest *
0x180011dea  mov     rcx, rsi; this
0x180011ded  call    ?SendRequest@EquationManager@@AEAAJAEBVUsbGipRequest@@@Z; EquationManager::SendRequest(UsbGipRequest const &)
0x180011df2  mov     edi, eax
0x180011df4  test    eax, eax
0x180011df6  jns     loc_180011E86
0x180011dfc  mov     ecx, cs:dword_180069000
0x180011e02  cmp     ecx, r15d
0x180011e05  jbe     short loc_180011E61
0x180011e07  mov     rdx, cs:qword_180069018
0x180011e0e  mov     rcx, cs:qword_180069010
0x180011e15  test    cl, 8
0x180011e18  jz      short loc_180011E61
0x180011e1a  mov     rax, rdx
0x180011e1d  and     eax, 8
0x180011e20  cmp     rax, rdx
0x180011e23  jnz     short loc_180011E61
0x180011e25  lea     rax, aOnecoreXboxGam_27; "onecore\\xbox\\gameinput\\feedback\\gip"...
0x180011e2c  mov     [rbp+57h+var_A0], edi
0x180011e2f  mov     [rbp+57h+var_98], rax
0x180011e33  lea     rdx, word_18005BF82
0x180011e3a  lea     rax, [rbp+57h+var_A0]
0x180011e3e  mov     [rbp+57h+var_9C], 14Ch
0x180011e45  mov     [rsp+0E0h+var_B0], rax
0x180011e4a  lea     rax, [rbp+57h+var_9C]
0x180011e4e  mov     [rsp+0E0h+var_B8], rax
0x180011e53  lea     rax, [rbp+57h+var_98]
0x180011e57  mov     [rsp+0E0h+var_C0], rax
0x180011e5c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180011e61  mov     rcx, [rbp+57h+P]; P
0x180011e65  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180011e69  jz      short loc_180011E70
0x180011e6b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180011e70  mov     rcx, rbx; lpCriticalSection
0x180011e73  call    cs:__imp_LeaveCriticalSection
0x180011e7a  nop     dword ptr [rax+rax+00h]
0x180011e7f  mov     eax, edi
0x180011e81  jmp     loc_180011F20
0x180011e86  xor     edx, edx
0x180011e88  lea     rax, [rdx+103h]
0x180011e8f  add     rax, rax
0x180011e92  mov     rcx, [rsi+rax*8]
0x180011e96  test    rcx, rcx
0x180011e99  jz      short loc_180011EF7
0x180011e9b  mov     r8d, [rbp+rdx*4+57h+var_70]
0x180011ea0  cmp     r8d, 0Fh
0x180011ea4  jz      short loc_180011EF7
0x180011ea6  mov     r10, [rsi+1180h]
0x180011ead  cmp     r8d, 1
0x180011eb1  jnz     short loc_180011EBD
0x180011eb3  mov     rax, [rcx+40h]
0x180011eb7  mov     [rcx+68h], rax
0x180011ebb  jmp     short loc_180011EEB
0x180011ebd  cmp     r8d, 3
0x180011ec1  jnz     short loc_180011EEB
0x180011ec3  cmp     qword ptr [rcx+40h], 0FFFFFFFFFFFFFFFFh
0x180011ec8  jz      short loc_180011EEB
0x180011eca  mov     r9, [rcx+68h]
0x180011ece  mov     rax, r14
0x180011ed1  sub     rax, [rcx+50h]
0x180011ed5  cmp     rax, r9
0x180011ed8  jb      short loc_180011EE4
0x180011eda  mov     qword ptr [rcx+68h], 0
0x180011ee2  jmp     short loc_180011EEB
0x180011ee4  sub     r9, rax
0x180011ee7  mov     [rcx+68h], r9
0x180011eeb  mov     [rcx+50h], r14
0x180011eef  mov     [rcx+58h], r8d
0x180011ef3  mov     [rcx+60h], r10
0x180011ef7  inc     rdx; struct std::nothrow_t *
0x180011efa  cmp     rdx, 10h
0x180011efe  jnz     short loc_180011E88
0x180011f00  mov     rcx, [rbp+57h+P]; P
0x180011f04  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180011f08  jz      short loc_180011F0F
0x180011f0a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180011f0f  mov     rcx, rbx; lpCriticalSection
0x180011f12  call    cs:__imp_LeaveCriticalSection
0x180011f19  nop     dword ptr [rax+rax+00h]
0x180011f1e  xor     eax, eax
0x180011f20  add     rsp, 0B8h
0x180011f27  pop     r15
0x180011f29  pop     r14
0x180011f2b  pop     rdi
0x180011f2c  pop     rsi
0x180011f2d  pop     rbx
0x180011f2e  pop     rbp
0x180011f2f  retn
0x180011f31  mov     edx, 69h ; 'i'
0x180011f36  mov     ecx, 8000FFFFh
0x180011f3b  call    GameInputFailFast
```
