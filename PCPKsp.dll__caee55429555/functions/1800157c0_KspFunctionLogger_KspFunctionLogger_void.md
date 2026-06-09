# KspFunctionLogger::~KspFunctionLogger(void)

- ea: `0x1800157c0`
- end: `0x1800159e6`
- name: `??1KspFunctionLogger@@QEAA@XZ`
- size: `550`
- prototype: `void __fastcall(KspFunctionLogger *__hidden this)`
- caller_count: `447`
- callee_count: `4`
- tags: ``

## callers

- `0x180002094`
- `0x18000d750`
- `0x18000dc90`
- `0x18000f240`
- `0x18000f880`
- `0x1800116d0`
- `0x180011c60`
- `0x180012640`
- `0x1800133f0`
- `0x1800138e0`
- `0x180013b00`
- `0x180013d60`
- `0x180014590`
- `0x180014bd0`
- `0x1800159f0`
- `0x180015ac0`
- `0x180018d8c`
- `0x180018e20`
- `0x180019ed4`
- `0x18001adf0`
- `0x18001b050`
- `0x18001b298`
- `0x18001b4a0`
- `0x18001b8f0`
- `0x18001bb00`
- `0x18001d590`
- `0x18001fed4`
- `0x180021310`
- `0x180021b7c`
- `0x1800222b4`
- `0x1800223c0`
- `0x180023894`
- `0x180023f98`
- `0x1800249d8`
- `0x180026830`
- `0x180026948`
- `0x180026b90`
- `0x180026e30`
- `0x180027210`
- `0x180027670`
- `0x18002809c`
- `0x180028bb0`
- `0x180028cd8`
- `0x180028f24`
- `0x1800293e0`
- `0x180029700`
- `0x180029a80`
- `0x180029f48`
- `0x18002a0b0`
- `0x18002a634`

## callees

- `0x1800157c0`
- `0x18003cf80`
- `0x180055ac4`
- `0x1800764d0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800158d5`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800158d5`

## pseudocode

```c
void __fastcall KspFunctionLogger::~KspFunctionLogger(int **this)
{
  __int64 v2; // r10
  int *v3; // rcx
  __int64 v4; // rax
  int v6; // eax
  int *v7; // rax
  _DWORD *v8; // rcx
  int v9; // r8d
  int v10; // r9d
  __int64 *v11; // rdx
  int v12; // eax
  _DWORD *v13; // rcx
  int v14; // r8d
  int v15; // r9d
  unsigned int v16; // edx
  unsigned int v17; // [rsp+40h] [rbp-29h] BYREF
  __int64 v18; // [rsp+48h] [rbp-21h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+50h] [rbp-19h] BYREF
  int v20; // [rsp+60h] [rbp-9h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+70h] [rbp+7h] BYREF
  int *v22; // [rsp+80h] [rbp+17h]
  int v23; // [rsp+88h] [rbp+1Fh]
  int v24; // [rsp+8Ch] [rbp+23h]
  __int64 *v25; // [rsp+90h] [rbp+27h]
  __int64 v26; // [rsp+98h] [rbp+2Fh]
  int *v27; // [rsp+A0h] [rbp+37h]
  int v28; // [rsp+A8h] [rbp+3Fh]
  int v29; // [rsp+ACh] [rbp+43h]

  if ( *((_BYTE *)this + 16) )
  {
    v2 = *((_QWORD *)KspDebugProvider::Instance() + 1);
    if ( *(_DWORD *)v2 > 5u )
    {
      v3 = *this;
      v18 = 0x1000000;
      if ( v3 )
      {
        v4 = -1;
        while ( *((_WORD *)v3 + ++v4) != 0 )
          ;
        v6 = 2 * v4 + 2;
      }
      else
      {
        v3 = &dword_1800DB714;
        v6 = 2;
      }
      v28 = v6;
      v27 = v3;
      v25 = &v18;
      *(_DWORD *)&EventDescriptor.Level = 5;
      UserData.Ptr = *(_QWORD *)(v2 + 8);
      v29 = 0;
      EventDescriptor.Keyword = 0;
      v26 = 8;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      UserData.Size = *(unsigned __int16 *)UserData.Ptr;
      v22 = &dword_1800F9EE4;
      UserData.Reserved = 2;
      v23 = 37;
      v24 = 1;
      v17 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(*(_QWORD *)(v2 + 32), &EventDescriptor, 0, 0, 4u, &UserData);
    }
    return;
  }
  v7 = this[1];
  v20 = 0;
  if ( !v7 )
  {
    this[1] = &v20;
    goto LABEL_11;
  }
  v12 = *v7;
  if ( v12 < 0 )
  {
    v8 = (_DWORD *)*((_QWORD *)KspDebugProvider::Instance() + 1);
    if ( *v8 <= 2u )
      return;
    v17 = *this[1];
    v11 = qword_1800F9E28;
    goto LABEL_19;
  }
  if ( (v12 & 0x40000000) == 0 )
  {
LABEL_11:
    v8 = (_DWORD *)*((_QWORD *)KspDebugProvider::Instance() + 1);
    if ( *v8 <= 5u )
      return;
    v17 = *this[1];
    v11 = (__int64 *)byte_1800F9E63;
LABEL_19:
    *(_QWORD *)&EventDescriptor.Id = *this;
    v18 = 0x1000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
      (_DWORD)v8,
      (_DWORD)v11,
      v9,
      v10,
      (__int64)&v18,
      (__int64)&EventDescriptor,
      (__int64)&v17);
    return;
  }
  v13 = (_DWORD *)*((_QWORD *)KspDebugProvider::Instance() + 1);
  if ( *v13 > 3u )
  {
    v16 = *this[1];
    v18 = (__int64)*this;
    v17 = v16;
    *(_QWORD *)&EventDescriptor.Id = 0x1000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
      (_DWORD)v13,
      (unsigned int)&word_1800F9E9E,
      v14,
      v15,
      (__int64)&EventDescriptor,
      (__int64)&v18,
      (__int64)&v17);
  }
}

```

## disassembly

```asm
0x1800157c0  mov     [rsp-8+arg_8], rbx
0x1800157c5  push    rbp
0x1800157c6  lea     rbp, [rsp-57h]
0x1800157cb  sub     rsp, 0C0h
0x1800157d2  mov     rax, cs:__security_cookie
0x1800157d9  xor     rax, rsp
0x1800157dc  mov     [rbp+57h+var_10], rax
0x1800157e0  cmp     byte ptr [rcx+10h], 0
0x1800157e4  mov     rbx, rcx
0x1800157e7  jz      loc_1800158E6
0x1800157ed  call    ?Instance@KspDebugProvider@@KAPEAV1@XZ; KspDebugProvider::Instance(void)
0x1800157f2  mov     r10, [rax+8]
0x1800157f6  mov     eax, [r10]
0x1800157f9  cmp     eax, 5
0x1800157fc  jbe     loc_1800159C8
0x180015802  mov     rcx, [rbx]
0x180015805  mov     [rbp+57h+var_78], 1000000h
0x18001580d  test    rcx, rcx
0x180015810  jz      short loc_180015835
0x180015812  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180015819  nop     dword ptr [rax+00000000h]
0x180015820  cmp     word ptr [rcx+rax*2+2], 0
0x180015826  lea     rax, [rax+1]
0x18001582a  jnz     short loc_180015820
0x18001582c  lea     eax, ds:2[rax*2]
0x180015833  jmp     short loc_180015841
0x180015835  lea     rcx, dword_1800DB714
0x18001583c  mov     eax, 2
0x180015841  mov     [rbp+57h+var_18], eax
0x180015844  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x180015848  mov     [rbp+57h+var_20], rcx
0x18001584c  lea     rax, [rbp+57h+var_78]
0x180015850  mov     [rbp+57h+var_30], rax
0x180015854  xor     ecx, ecx
0x180015856  movzx   eax, cs:word_1800F9EDA
0x18001585d  xor     r9d, r9d; RelatedActivityId
0x180015860  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x180015863  xor     r8d, r8d; ActivityId
0x180015866  mov     rax, [r10+8]
0x18001586a  mov     [rbp+57h+var_50.Ptr], rax
0x18001586e  mov     [rbp+57h+var_14], ecx
0x180015871  mov     [rbp+57h+EventDescriptor.Keyword], rcx
0x180015875  lea     rcx, _TraceLoggingMetadata
0x18001587c  mov     [rbp+57h+var_28], 8
0x180015884  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x18001588b  movzx   eax, word ptr [rax]
0x18001588e  mov     [rbp+57h+var_50.Size], eax
0x180015891  lea     rax, dword_1800F9EE4
0x180015898  mov     [rbp+57h+var_40], rax
0x18001589c  lea     rax, _TraceLoggingMetadataEnd
0x1800158a3  sub     eax, ecx
0x1800158a5  mov     dword ptr [rbp+57h+var_50.0Ch], 2
0x1800158ac  mov     [rbp+57h+var_38], 25h ; '%'
0x1800158b3  mov     [rbp+57h+var_34], 1
0x1800158ba  mov     [rbp+57h+var_80], eax
0x1800158bd  mov     eax, [rbp+57h+var_80]
0x1800158c0  mov     rcx, [r10+20h]; RegHandle
0x1800158c4  lea     rax, [rbp+57h+var_50]
0x1800158c8  mov     [rsp+0C0h+UserData], rax; UserData
0x1800158cd  mov     [rsp+0C0h+UserDataCount], 4; UserDataCount
0x1800158d5  call    cs:__imp_EventWriteTransfer
0x1800158dc  nop     dword ptr [rax+rax+00h]
0x1800158e1  jmp     loc_1800159C8
0x1800158e6  mov     rax, [rbx+8]
0x1800158ea  xor     ecx, ecx
0x1800158ec  mov     [rbp+57h+var_60], ecx
0x1800158ef  test    rax, rax
0x1800158f2  jnz     short loc_180015922
0x1800158f4  lea     rax, [rbp+57h+var_60]
0x1800158f8  mov     [rbx+8], rax
0x1800158fc  call    ?Instance@KspDebugProvider@@KAPEAV1@XZ; KspDebugProvider::Instance(void)
0x180015901  mov     rcx, [rax+8]
0x180015905  mov     eax, [rcx]
0x180015907  cmp     eax, 5
0x18001590a  jbe     loc_1800159C8
0x180015910  mov     rax, [rbx+8]
0x180015914  mov     edx, [rax]
0x180015916  mov     [rbp+57h+var_80], edx
0x180015919  lea     rdx, byte_1800F9E63
0x180015920  jmp     short loc_180015999
0x180015922  mov     eax, [rax]
0x180015924  test    eax, eax
0x180015926  js      short loc_180015979
0x180015928  bt      eax, 1Eh
0x18001592c  jnb     short loc_1800158FC
0x18001592e  call    ?Instance@KspDebugProvider@@KAPEAV1@XZ; KspDebugProvider::Instance(void)
0x180015933  mov     rcx, [rax+8]
0x180015937  mov     eax, [rcx]
0x180015939  cmp     eax, 3
0x18001593c  jbe     loc_1800159C8
0x180015942  mov     rax, [rbx+8]
0x180015946  mov     edx, [rax]
0x180015948  mov     rax, [rbx]
0x18001594b  mov     [rbp+57h+var_78], rax
0x18001594f  lea     rax, [rbp+57h+var_80]
0x180015953  mov     [rsp+0C0h+var_90], rax
0x180015958  lea     rax, [rbp+57h+var_78]
0x18001595c  mov     [rsp+0C0h+UserData], rax
0x180015961  lea     rax, [rbp+57h+EventDescriptor]
0x180015965  mov     [rbp+57h+var_80], edx
0x180015968  lea     rdx, word_1800F9E9E
0x18001596f  mov     qword ptr [rbp+57h+EventDescriptor.Id], 1000000h
0x180015977  jmp     short loc_1800159BE
0x180015979  call    ?Instance@KspDebugProvider@@KAPEAV1@XZ; KspDebugProvider::Instance(void)
0x18001597e  mov     rcx, [rax+8]
0x180015982  mov     eax, [rcx]
0x180015984  cmp     eax, 2
0x180015987  jbe     short loc_1800159C8
0x180015989  mov     rax, [rbx+8]
0x18001598d  mov     edx, [rax]
0x18001598f  mov     [rbp+57h+var_80], edx
0x180015992  lea     rdx, qword_1800F9E28
0x180015999  mov     rax, [rbx]
0x18001599c  mov     qword ptr [rbp+57h+EventDescriptor.Id], rax
0x1800159a0  lea     rax, [rbp+57h+var_80]
0x1800159a4  mov     [rsp+0C0h+var_90], rax
0x1800159a9  lea     rax, [rbp+57h+EventDescriptor]
0x1800159ad  mov     [rsp+0C0h+UserData], rax
0x1800159b2  lea     rax, [rbp+57h+var_78]
0x1800159b6  mov     [rbp+57h+var_78], 1000000h
0x1800159be  mov     qword ptr [rsp+0C0h+UserDataCount], rax
0x1800159c3  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x1800159c8  mov     rcx, [rbp+57h+var_10]
0x1800159cc  xor     rcx, rsp; StackCookie
0x1800159cf  call    __security_check_cookie
0x1800159d4  mov     rbx, [rsp+0C0h+arg_8]
0x1800159dc  add     rsp, 0C0h
0x1800159e3  pop     rbp
0x1800159e4  retn
```
