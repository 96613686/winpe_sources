# CReader::PowerUp(void)

- ea: `0x180003ff0`
- end: `0x1800044cc`
- name: `?PowerUp@CReader@@IEAAXXZ`
- size: `1244`
- prototype: `void __fastcall(CReader *__hidden this)`
- caller_count: `5`
- callee_count: `13`
- tags: ``

## callers

- `0x180001950`
- `0x1800039e0`
- `0x18000ecb0`
- `0x18002c070`
- `0x18002dcc4`

## callees

- `0x180003458`
- `0x18000366c`
- `0x180003ff0`
- `0x1800044e0`
- `0x180008f80`
- `0x18000d7a0`
- `0x18000f1c0`
- `0x180018658`
- `0x180018f84`
- `0x18002d7c8`
- `0x18002db7c`
- `0x18002dbd8`
- `0x18003261b`

## pseudocode

```c
void __fastcall CReader::PowerUp(CReader *this)
{
  CReader *v1; // rbx
  struct CBuffer *v2; // r8
  unsigned int *v3; // r9
  int ReaderState; // eax
  int v5; // eax
  ulong v6; // eax
  unsigned int v7; // ecx
  const unsigned __int8 *v8; // rax
  _DWORD *v10; // [rsp+38h] [rbp-80h]
  int v11; // [rsp+40h] [rbp-78h]
  int v12; // [rsp+44h] [rbp-74h]
  unsigned int v13; // [rsp+48h] [rbp-70h] BYREF
  _DWORD *v14; // [rsp+50h] [rbp-68h]
  ulong pExceptionObject; // [rsp+58h] [rbp-60h] BYREF
  ulong v16; // [rsp+5Ch] [rbp-5Ch] BYREF
  ulong v17; // [rsp+60h] [rbp-58h] BYREF
  ulong v18; // [rsp+64h] [rbp-54h] BYREF
  ulong v19; // [rsp+68h] [rbp-50h] BYREF
  ulong v20; // [rsp+6Ch] [rbp-4Ch] BYREF
  ulong v21; // [rsp+70h] [rbp-48h] BYREF
  struct CBuffer *v22; // [rsp+78h] [rbp-40h]
  _BYTE v23[8]; // [rsp+80h] [rbp-38h] BYREF
  ulong v24; // [rsp+88h] [rbp-30h] BYREF
  ulong v25; // [rsp+8Ch] [rbp-2Ch] BYREF
  ulong v26; // [rsp+90h] [rbp-28h] BYREF
  ulong v27; // [rsp+94h] [rbp-24h] BYREF
  int v29; // [rsp+C8h] [rbp+10h]
  int *v30; // [rsp+C8h] [rbp+10h]
  int v31; // [rsp+D0h] [rbp+18h]

  v1 = this;
  v29 = 0;
  v11 = 0;
  v13 = 0;
  v31 = 3;
  CLockWrite::CLockWrite((CLockWrite *)v23, (CReader *)((char *)this + 56));
  v14 = (_DWORD *)((char *)v1 + 228);
  while ( 1 )
  {
    v10 = v14;
    if ( v29 )
      break;
    ReaderState = CReader::GetReaderState(v1);
    if ( ReaderState == v11 )
    {
      if ( v31 == 1 )
      {
        *((_DWORD *)this + 46) = 0;
        *v14 = 0;
        CReader::SetAvailabilityStatus(v1, 4);
        pExceptionObject = -2146435044;
        throw &pExceptionObject;
      }
      --v31;
    }
    else
    {
      v11 = ReaderState;
      v31 = 3;
    }
    if ( ReaderState == 6 )
    {
      v30 = (int *)((char *)v1 + 192);
      if ( *((int *)v1 + 48) < 8 )
      {
        v2 = (CReader *)((char *)v1 + 168);
        if ( *((_DWORD *)v1 + 46) < 2u )
        {
          try
          {
            CReader::GetReaderAttr(v1, 590595, v2, (unsigned int)v3);
          }
          catch ( ulong v26 )
          {
            CReader::SetAvailabilityStatus(this, 3);
            *((_DWORD *)this + 46) = 0;
            *((_DWORD *)this + 57) = 0;
            v1 = this;
          }
          catch ( ... )
          {
            CReader::SetAvailabilityStatus(this, 3);
            *((_DWORD *)this + 46) = 0;
            *((_DWORD *)this + 57) = 0;
            v1 = this;
          }
        }
        if ( !*v10 )
        {
          try
          {
            *v10 = CReader::GetReaderAttr(v1, 524801, (unsigned int)v2);
          }
          catch ( ulong v27 )
          {
            v1 = this;
          }
          catch ( ... )
          {
            v1 = this;
          }
        }
      }
      if ( *v30 < 5 )
      {
        CReader::SetAvailabilityStatus(v1, 5);
        CReader::SetActive(v1, 0);
      }
      v29 = 1;
    }
    else
    {
      switch ( ReaderState )
      {
        case 0:
          v17 = -2146435071;
          throw &v17;
        case 1:
          *((_DWORD *)this + 46) = 0;
          *v14 = 0;
          ++*((_DWORD *)this + 50);
          if ( *((int *)v1 + 48) < 8 )
            CReader::SetAvailabilityStatus(v1, 1);
          v16 = -2146435060;
          throw &v16;
        case 2:
          *((_DWORD *)this + 46) = 0;
          *v14 = 0;
          v5 = *((_DWORD *)v1 + 8);
          if ( (v5 & 1) == 0 )
            goto LABEL_14;
          try
          {
            CReader::ReaderSwallow(v1);
          }
          catch ( ulong v20 )
          {
            if ( v20 == 50 )
              *((_DWORD *)this + 8) &= ~1u;
            v1 = this;
            goto LABEL_14;
          }
          catch ( ... )
          {
            v1 = this;
            goto LABEL_14;
          }
          break;
        case 3:
LABEL_14:
          v22 = (CReader *)((char *)v1 + 168);
          *((_DWORD *)v1 + 46) = 0;
          *v10 = 0;
          v12 = 3;
          do
          {
            try
            {
              CReader::ReaderColdReset(v1, v22);
              v6 = 0;
            }
            catch ( ulong v21 )
            {
              v6 = v21;
              v1 = this;
            }
            catch ( ... )
            {
              v6 = -2146435071;
              v1 = this;
            }
            --v12;
          }
          while ( v12 && v6 );
          if ( v6 )
          {
            *((_DWORD *)this + 46) = 0;
            if ( *((int *)this + 48) < 8 )
              CReader::SetAvailabilityStatus(v1, 3);
            v29 = 1;
          }
          else if ( *((int *)this + 48) < 5 )
          {
            CReader::SetAvailabilityStatus(v1, 5);
            CReader::SetActive(v1, 0);
          }
          *v10 = 0;
          ++*((_DWORD *)this + 51);
          break;
        case 4:
          *((_DWORD *)v1 + 46) = 0;
          *v10 = 0;
          try
          {
            CReader::ReaderWarmReset(v1, (CReader *)((char *)v1 + 168));
            if ( *((int *)v1 + 48) < 5 )
            {
              CReader::SetAvailabilityStatus(v1, 5);
              CReader::SetActive(v1, 0);
            }
          }
          catch ( ulong v24 )
          {
            if ( *((int *)this + 48) < 8 )
              CReader::SetAvailabilityStatus(this, 3);
            *((_DWORD *)this + 46) = 0;
            v1 = this;
          }
          catch ( ... )
          {
            if ( *((int *)this + 48) < 8 )
              CReader::SetAvailabilityStatus(this, 3);
            *((_DWORD *)this + 46) = 0;
            v1 = this;
          }
          *v10 = 0;
          ++*((_DWORD *)this + 51);
          break;
        case 5:
          if ( *((int *)v1 + 48) < 8 )
          {
            v2 = (CReader *)((char *)v1 + 168);
            if ( *((_DWORD *)v1 + 46) < 2u )
            {
              try
              {
                CReader::GetReaderAttr(v1, 590595, v2, (unsigned int)v3);
                if ( *((int *)v1 + 48) < 5 )
                {
                  CReader::SetAvailabilityStatus(v1, 5);
                  CReader::SetActive(v1, 0);
                }
              }
              catch ( ulong v25 )
              {
                CReader::SetAvailabilityStatus(this, 3);
                *((_DWORD *)this + 46) = 0;
                v1 = this;
              }
              catch ( ... )
              {
                CReader::SetAvailabilityStatus(this, 3);
                *((_DWORD *)this + 46) = 0;
                v1 = this;
              }
            }
          }
          *v10 = 0;
          v29 = 1;
          break;
        default:
          v18 = -2146435071;
          throw &v18;
      }
    }
  }
  if ( *((int *)v1 + 48) < 8 )
  {
    v7 = *((_DWORD *)this + 46);
    if ( v7 )
    {
      v8 = *((_DWORD *)this + 47) ? (const unsigned __int8 *)*((_QWORD *)this + 22) : (const unsigned __int8 *)&Data;
      if ( !(unsigned int)ParseAtr(v8, &v13, (unsigned int *)v2, v3, v7) || *((_DWORD *)this + 46) != v13 )
      {
        *v10 = 0;
        CReader::SetAvailabilityStatus(v1, 4);
        v19 = -2146435044;
        throw &v19;
      }
    }
  }
  CLockWrite::~CLockWrite((CLockWrite *)v23);
}

```

## disassembly

```asm
0x180003ff0  mov     [rsp+arg_0], rcx
0x180003ff5  push    rbx
0x180003ff6  push    rsi
0x180003ff7  push    rdi
0x180003ff8  sub     rsp, 0A0h
0x180003fff  mov     rbx, rcx
0x180004002  mov     [rsp+0B8h+var_88], rcx
0x180004007  mov     dword ptr [rsp+0B8h+arg_8], 0
0x180004012  mov     [rsp+0B8h+var_78], 0
0x18000401a  mov     [rsp+0B8h+var_70], 0
0x180004022  mov     [rsp+0B8h+arg_10], 3
0x18000402d  lea     rdx, [rcx+38h]; struct CAccessLock *
0x180004031  lea     rcx, [rsp+0B8h+var_38]; this
0x180004039  call    ??0CLockWrite@@QEAA@PEAVCAccessLock@@@Z; CLockWrite::CLockWrite(CAccessLock *)
0x18000403e  nop
0x18000403f  lea     rax, [rbx+0E4h]
0x180004046  mov     [rsp+0B8h+var_68], rax
0x18000404b  lea     rsi, cs:180000000h
0x180004052  mov     rax, [rsp+0B8h+var_68]
0x180004057  mov     [rsp+0B8h+var_80], rax
0x18000405c  cmp     dword ptr [rsp+0B8h+arg_8], 0
0x180004064  jnz     loc_180004410
0x18000406a  mov     rcx, rbx; this
0x18000406d  call    ?GetReaderState@CReader@@QEAAKXZ; CReader::GetReaderState(void)
0x180004072  mov     ecx, eax
0x180004074  cmp     eax, [rsp+0B8h+var_78]
0x180004078  jz      short loc_18000408B
0x18000407a  mov     [rsp+0B8h+var_78], eax
0x18000407e  mov     [rsp+0B8h+arg_10], 3
0x180004089  jmp     short loc_1800040DF
0x18000408b  mov     eax, [rsp+0B8h+arg_10]
0x180004092  sub     eax, 1
0x180004095  jnz     short loc_1800040D8
0x180004097  mov     rax, [rsp+0B8h+var_88]
0x18000409c  mov     dword ptr [rax+0B8h], 0
0x1800040a6  mov     rax, [rsp+0B8h+var_68]
0x1800040ab  mov     dword ptr [rax], 0
0x1800040b1  mov     edx, 4
0x1800040b6  mov     rcx, rbx
0x1800040b9  call    ?SetAvailabilityStatus@CReader@@IEAAXW4AvailableState@1@@Z; CReader::SetAvailabilityStatus(CReader::AvailableState)
0x1800040be  mov     [rsp+0B8h+pExceptionObject], 8010001Ch
0x1800040c6  lea     rdx, _TI1K; pThrowInfo
0x1800040cd  lea     rcx, [rsp+0B8h+pExceptionObject]; pExceptionObject
0x1800040d2  call    _CxxThrowException_0
0x1800040d8  mov     [rsp+0B8h+arg_10], eax
0x1800040df  cmp     ecx, 6
0x1800040e2  jz      loc_18000436D
0x1800040e8  cmp     ecx, 5; switch 6 cases
0x1800040eb  ja      def_1800040FB; jumptable 00000001800040FB default case
0x1800040f1  mov     eax, ds:(jpt_1800040FB - 180000000h)[rsi+rcx*4]
0x1800040f8  add     rax, rsi
0x1800040fb  jmp     rax; switch jump
0x1800040fd  mov     rdi, [rsp+0B8h+var_88]; jumptable 00000001800040FB case 1
0x180004102  mov     dword ptr [rdi+0B8h], 0
0x18000410c  mov     rax, [rsp+0B8h+var_68]
0x180004111  mov     dword ptr [rax], 0
0x180004117  inc     dword ptr [rdi+0C8h]
0x18000411d  cmp     dword ptr [rbx+0C0h], 8
0x180004124  jge     short loc_180004133
0x180004126  mov     edx, 1
0x18000412b  mov     rcx, rbx
0x18000412e  call    ?SetAvailabilityStatus@CReader@@IEAAXW4AvailableState@1@@Z; CReader::SetAvailabilityStatus(CReader::AvailableState)
0x180004133  mov     [rsp+0B8h+var_5C], 8010000Ch
0x18000413b  lea     rdx, _TI1K; pThrowInfo
0x180004142  lea     rcx, [rsp+0B8h+var_5C]; pExceptionObject
0x180004147  call    _CxxThrowException_0
0x18000414d  mov     rax, [rsp+0B8h+var_88]; jumptable 00000001800040FB case 2
0x180004152  mov     dword ptr [rax+0B8h], 0
0x18000415c  mov     rax, [rsp+0B8h+var_68]
0x180004161  mov     dword ptr [rax], 0
0x180004167  mov     eax, [rbx+20h]
0x18000416a  test    al, 1
0x18000416c  jz      short loc_18000418D; jumptable 00000001800040FB case 3
0x18000416e  mov     rcx, rbx; this
0x180004171  call    ?ReaderSwallow@CReader@@QEAAXXZ; CReader::ReaderSwallow(void)
0x180004176  nop
0x180004177  jmp     loc_180004052
0x18000417c  jmp     short $+2
0x18000417e  mov     rbx, [rsp+0B8h+arg_0]
0x180004186  lea     rsi, cs:180000000h
0x18000418d  lea     rax, [rbx+0A8h]; jumptable 00000001800040FB case 3
0x180004194  mov     [rsp+0B8h+var_40], rax
0x180004199  mov     dword ptr [rax+10h], 0
0x1800041a0  mov     rax, [rsp+0B8h+var_80]
0x1800041a5  mov     dword ptr [rax], 0
0x1800041ab  mov     [rsp+0B8h+var_74], 3
0x1800041b3  mov     rdx, [rsp+0B8h+var_40]; struct CBuffer *
0x1800041b8  mov     rcx, rbx; this
0x1800041bb  call    ?ReaderColdReset@CReader@@QEAAXAEAVCBuffer@@@Z; CReader::ReaderColdReset(CBuffer &)
0x1800041c0  xor     eax, eax
0x1800041c2  jmp     short loc_1800041DC
0x1800041c4  jmp     short $+2
0x1800041c6  mov     eax, [rsp+0B8h+arg_18]
0x1800041cd  mov     rbx, [rsp+0B8h+arg_0]
0x1800041d5  lea     rsi, cs:180000000h
0x1800041dc  add     [rsp+0B8h+var_74], 0FFFFFFFFh
0x1800041e1  jz      short loc_1800041E7
0x1800041e3  test    eax, eax
0x1800041e5  jnz     short loc_1800041B3
0x1800041e7  mov     rdi, [rsp+0B8h+var_88]
0x1800041ec  test    eax, eax
0x1800041ee  jz      short loc_18000421D
0x1800041f0  mov     dword ptr [rdi+0B8h], 0
0x1800041fa  cmp     dword ptr [rdi+0C0h], 8
0x180004201  jge     short loc_180004210
0x180004203  mov     edx, 3
0x180004208  mov     rcx, rbx
0x18000420b  call    ?SetAvailabilityStatus@CReader@@IEAAXW4AvailableState@1@@Z; CReader::SetAvailabilityStatus(CReader::AvailableState)
0x180004210  mov     dword ptr [rsp+0B8h+arg_8], 1
0x18000421b  jmp     short loc_18000423D
0x18000421d  cmp     dword ptr [rdi+0C0h], 5
0x180004224  jge     short loc_18000423D
0x180004226  mov     edx, 5
0x18000422b  mov     rcx, rbx
0x18000422e  call    ?SetAvailabilityStatus@CReader@@IEAAXW4AvailableState@1@@Z; CReader::SetAvailabilityStatus(CReader::AvailableState)
0x180004233  xor     edx, edx; unsigned int
0x180004235  mov     rcx, rbx; this
0x180004238  call    ?SetActive@CReader@@QEAAXH@Z; CReader::SetActive(int)
0x18000423d  mov     rax, [rsp+0B8h+var_80]
0x180004242  mov     dword ptr [rax], 0
0x180004248  mov     rax, rdi
0x18000424b  inc     dword ptr [rax+0CCh]
0x180004251  jmp     loc_180004052
0x180004256  lea     rdx, [rbx+0A8h]; jumptable 00000001800040FB case 4
0x18000425d  mov     dword ptr [rdx+10h], 0
0x180004264  mov     rax, [rsp+0B8h+var_80]
0x180004269  mov     dword ptr [rax], 0
0x18000426f  mov     rcx, rbx; this
0x180004272  call    ?ReaderWarmReset@CReader@@QEAAXAEAVCBuffer@@@Z; CReader::ReaderWarmReset(CBuffer &)
0x180004277  cmp     dword ptr [rbx+0C0h], 5
0x18000427e  jge     short loc_180004298
0x180004280  mov     edx, 5
0x180004285  mov     rcx, rbx
0x180004288  call    ?SetAvailabilityStatus@CReader@@IEAAXW4AvailableState@1@@Z; CReader::SetAvailabilityStatus(CReader::AvailableState)
0x18000428d  xor     edx, edx; unsigned int
0x18000428f  mov     rcx, rbx; this
0x180004292  call    ?SetActive@CReader@@QEAAXH@Z; CReader::SetActive(int)
0x180004297  nop
0x180004298  jmp     short loc_1800042AB
0x18000429a  jmp     short $+2
0x18000429c  mov     rbx, [rsp+0B8h+arg_0]
0x1800042a4  lea     rsi, cs:180000000h
0x1800042ab  mov     rax, [rsp+0B8h+var_80]
0x1800042b0  mov     dword ptr [rax], 0
0x1800042b6  mov     rax, [rsp+0B8h+var_88]
0x1800042bb  inc     dword ptr [rax+0CCh]
0x1800042c1  jmp     loc_180004052
0x1800042c6  cmp     dword ptr [rbx+0C0h], 8; jumptable 00000001800040FB case 5
0x1800042cd  jge     short loc_18000431E
0x1800042cf  lea     r8, [rbx+0A8h]; struct CBuffer *
0x1800042d6  cmp     dword ptr [r8+10h], 2
0x1800042db  jnb     short loc_18000431E
0x1800042dd  mov     edx, 90303h; unsigned int
0x1800042e2  mov     rcx, rbx; this
0x1800042e5  call    ?GetReaderAttr@CReader@@QEAAXKAEAVCBuffer@@H@Z; CReader::GetReaderAttr(ulong,CBuffer &,int)
0x1800042ea  cmp     dword ptr [rbx+0C0h], 5
0x1800042f1  jge     short loc_18000430B
0x1800042f3  mov     edx, 5
0x1800042f8  mov     rcx, rbx
0x1800042fb  call    ?SetAvailabilityStatus@CReader@@IEAAXW4AvailableState@1@@Z; CReader::SetAvailabilityStatus(CReader::AvailableState)
0x180004300  xor     edx, edx; unsigned int
0x180004302  mov     rcx, rbx; this
0x180004305  call    ?SetActive@CReader@@QEAAXH@Z; CReader::SetActive(int)
0x18000430a  nop
0x18000430b  jmp     short loc_18000431E
0x18000430d  jmp     short $+2
0x18000430f  mov     rbx, [rsp+0B8h+arg_0]
0x180004317  lea     rsi, cs:180000000h
0x18000431e  mov     rax, [rsp+0B8h+var_80]
0x180004323  mov     dword ptr [rax], 0
0x180004329  mov     dword ptr [rsp+0B8h+arg_8], 1
0x180004334  jmp     loc_180004052
0x180004339  mov     [rsp+0B8h+var_58], 80100001h; jumptable 00000001800040FB case 0
0x180004341  lea     rdx, _TI1K; pThrowInfo
0x180004348  lea     rcx, [rsp+0B8h+var_58]; pExceptionObject
0x18000434d  call    _CxxThrowException_0
0x180004353  mov     [rsp+0B8h+var_54], 80100001h; jumptable 00000001800040FB default case
0x18000435b  lea     rdx, _TI1K; pThrowInfo
0x180004362  lea     rcx, [rsp+0B8h+var_54]; pExceptionObject
0x180004367  call    _CxxThrowException_0
0x18000436d  lea     rax, [rbx+0C0h]
0x180004374  mov     [rsp+0B8h+arg_8], rax
0x18000437c  cmp     dword ptr [rax], 8
0x18000437f  jge     short loc_1800043DC
0x180004381  lea     r8, [rbx+0A8h]; struct CBuffer *
0x180004388  cmp     dword ptr [r8+10h], 2
0x18000438d  jnb     short loc_1800043B0
0x18000438f  mov     edx, 90303h; unsigned int
0x180004394  mov     rcx, rbx; this
0x180004397  call    ?GetReaderAttr@CReader@@QEAAXKAEAVCBuffer@@H@Z; CReader::GetReaderAttr(ulong,CBuffer &,int)
0x18000439c  nop
0x18000439d  jmp     short loc_1800043B0
0x18000439f  jmp     short $+2
0x1800043a1  mov     rbx, [rsp+0B8h+arg_0]
0x1800043a9  lea     rsi, cs:180000000h
0x1800043b0  mov     rdi, [rsp+0B8h+var_80]
0x1800043b5  cmp     dword ptr [rdi], 0
0x1800043b8  jnz     short loc_1800043DC
0x1800043ba  mov     edx, 80201h; unsigned int
0x1800043bf  mov     rcx, rbx; this
0x1800043c2  call    ?GetReaderAttr@CReader@@QEAAKKH@Z; CReader::GetReaderAttr(ulong,int)
0x1800043c7  mov     [rdi], eax
0x1800043c9  jmp     short loc_1800043DC
0x1800043cb  jmp     short $+2
0x1800043cd  mov     rbx, [rsp+0B8h+arg_0]
0x1800043d5  lea     rsi, cs:180000000h
0x1800043dc  mov     rax, [rsp+0B8h+arg_8]
0x1800043e4  cmp     dword ptr [rax], 5
0x1800043e7  jge     short loc_180004400
0x1800043e9  mov     edx, 5
0x1800043ee  mov     rcx, rbx
0x1800043f1  call    ?SetAvailabilityStatus@CReader@@IEAAXW4AvailableState@1@@Z; CReader::SetAvailabilityStatus(CReader::AvailableState)
0x1800043f6  xor     edx, edx; unsigned int
0x1800043f8  mov     rcx, rbx; this
0x1800043fb  call    ?SetActive@CReader@@QEAAXH@Z; CReader::SetActive(int)
0x180004400  mov     dword ptr [rsp+0B8h+arg_8], 1
0x18000440b  jmp     loc_180004052
0x180004410  cmp     dword ptr [rbx+0C0h], 8
0x180004417  jge     loc_18000449B
0x18000441d  mov     rdi, [rsp+0B8h+var_88]
0x180004422  mov     ecx, [rdi+0B8h]
0x180004428  test    ecx, ecx
0x18000442a  jz      short loc_18000449B
0x18000442c  cmp     dword ptr [rdi+0BCh], 0
0x180004433  ja      short loc_18000443E
0x180004435  lea     rax, Data
0x18000443c  jmp     short loc_180004448
0x18000443e  mov     rax, rdi
0x180004441  mov     rax, [rax+0B0h]
0x180004448  mov     [rsp+0B8h+var_98], ecx; unsigned int
0x18000444c  lea     rdx, [rsp+0B8h+var_70]; unsigned int *
0x180004451  mov     rcx, rax; unsigned __int8 *
0x180004454  call    ?ParseAtr@@YAHPEBEPEAK11K@Z; ParseAtr(uchar const *,ulong *,ulong *,ulong *,ulong)
0x180004459  test    eax, eax
0x18000445b  jz      short loc_180004469
0x18000445d  mov     eax, [rsp+0B8h+var_70]
0x180004461  cmp     [rdi+0B8h], eax
0x180004467  jz      short loc_18000449B
0x180004469  mov     rax, [rsp+0B8h+var_80]
0x18000446e  mov     dword ptr [rax], 0
0x180004474  mov     edx, 4
0x180004479  mov     rcx, rbx
0x18000447c  call    ?SetAvailabilityStatus@CReader@@IEAAXW4AvailableState@1@@Z; CReader::SetAvailabilityStatus(CReader::AvailableState)
0x180004481  mov     [rsp+0B8h+var_50], 8010001Ch
0x180004489  lea     rdx, _TI1K; pThrowInfo
0x180004490  lea     rcx, [rsp+0B8h+var_50]; pExceptionObject
0x180004495  call    _CxxThrowException_0
0x18000449b  lea     rcx, [rsp+0B8h+var_38]; this
0x1800044a3  call    ??1CLockWrite@@QEAA@XZ; CLockWrite::~CLockWrite(void)
0x1800044a8  add     rsp, 0A0h
0x1800044af  pop     rdi
0x1800044b0  pop     rsi
0x1800044b1  pop     rbx
0x1800044b2  retn
```
