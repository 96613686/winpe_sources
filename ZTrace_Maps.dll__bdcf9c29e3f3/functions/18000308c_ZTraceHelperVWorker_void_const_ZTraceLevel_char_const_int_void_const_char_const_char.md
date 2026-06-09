# ZTraceHelperVWorker(void const *,ZTraceLevel,char const *,int,void const *,char const *,char *)

- ea: `0x18000308c`
- end: `0x1800032ed`
- name: `?ZTraceHelperVWorker@@YAXPEBXW4ZTraceLevel@@PEBDH02PEAD@Z`
- size: `609`
- prototype: `void __fastcall(__int64, unsigned int, const char *, unsigned int, const void *, char *Format, va_list ArgList)`
- caller_count: `4`
- callee_count: `7`
- tags: ``

## callers

- `0x180002fc0`
- `0x180003000`
- `0x180003040`
- `0x180003080`

## callees

- `0x18000108c`
- `0x180001730`
- `0x1800022d8`
- `0x180002bd4`
- `0x180002d8c`
- `0x180002f80`
- `0x18000308c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800030de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800030de`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800032bd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800032bd`

## pseudocode

```c
void __fastcall ZTraceHelperVWorker(
        __int64 a1,
        unsigned int a2,
        const char *a3,
        unsigned int a4,
        const void *a5,
        char *Format,
        va_list ArgList)
{
  DWORD LastError; // ebx
  __int64 v11; // r8
  __int64 v12; // r9
  __int64 v13; // r8
  __int64 v14; // r9
  unsigned int v15; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v16; // [rsp+54h] [rbp-ACh] BYREF
  BOOL v17; // [rsp+58h] [rbp-A8h]
  __int64 v18; // [rsp+60h] [rbp-A0h] BYREF
  char *v19; // [rsp+68h] [rbp-98h] BYREF
  __int64 v20; // [rsp+70h] [rbp-90h] BYREF
  const void *v21; // [rsp+78h] [rbp-88h]
  char Buffer[1024]; // [rsp+80h] [rbp-80h] BYREF

  v21 = a5;
  LastError = GetLastError();
  v17 = ZTraceEnabledHelper(a2);
  if ( v17 || a2 <= 1 )
  {
    if ( (unsigned int)vsnprintf(Buffer, 0x3FFu, Format, ArgList) > 0x3FE )
      Buffer[1023] = 0;
    if ( a2 <= 1 )
    {
      if ( a2 )
      {
        if ( (unsigned int)dword_180007000 > 5
          && (qword_180007010 & 0x400000000000LL) != 0
          && (qword_180007018 & 0x400000000000LL) == qword_180007018 )
        {
          v20 = 0x2000000;
          v19 = Buffer;
          v16 = a4;
          v18 = (__int64)a3;
          v15 = a2;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
            0x400000000000LL,
            (__int64)byte_180005AB9,
            v11,
            v12,
            (__int64)&v15,
            &v18,
            (__int64)&v16,
            &v19);
        }
      }
      else if ( UnderErrorUploadLimit(0, a3, a4, Buffer)
             && (unsigned int)dword_180007000 > 5
             && (qword_180007010 & 0x400000000000LL) != 0
             && (qword_180007018 & 0x400000000000LL) == qword_180007018 )
      {
        v18 = 50331648;
        v19 = Buffer;
        v15 = a4;
        v20 = (__int64)a3;
        v16 = 0;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
          0x400000000000LL,
          (__int64)byte_180005B09,
          v13,
          v14,
          (__int64)&v16,
          &v20,
          (__int64)&v15,
          &v19);
      }
    }
    if ( v17 && qword_1800072B8 )
      ZTracer::Trace(qword_1800072B8, a2, a3, a4, v21, Buffer);
  }
  SetLastError(LastError);
}

```

## disassembly

```asm
0x18000308c  mov     [rsp-8+arg_0], rbx
0x180003091  push    rbp
0x180003092  push    rsi
0x180003093  push    rdi
0x180003094  push    r12
0x180003096  push    r13
0x180003098  push    r14
0x18000309a  push    r15
0x18000309c  lea     rbp, [rsp-390h]
0x1800030a4  sub     rsp, 490h
0x1800030ab  mov     rax, cs:__security_cookie
0x1800030b2  xor     rax, rsp
0x1800030b5  mov     [rbp+3C0h+var_40], rax
0x1800030bc  mov     rax, [rbp+3C0h+arg_20]
0x1800030c3  mov     r15d, r9d
0x1800030c6  mov     r12, [rbp+3C0h+Format]
0x1800030cd  mov     r14, r8
0x1800030d0  mov     r13, [rbp+3C0h+ArgList]
0x1800030d7  mov     esi, edx
0x1800030d9  mov     [rsp+4C0h+var_448], rax
0x1800030de  call    cs:__imp_GetLastError
0x1800030e4  xor     edi, edi
0x1800030e6  mov     ecx, esi
0x1800030e8  cmp     esi, 1
0x1800030eb  mov     ebx, eax
0x1800030ed  setbe   dil
0x1800030f1  call    ?ZTraceEnabledHelper@@YAHW4ZTraceLevel@@@Z; ZTraceEnabledHelper(ZTraceLevel)
0x1800030f6  mov     [rsp+4C0h+var_468], eax
0x1800030fa  test    eax, eax
0x1800030fc  jnz     short loc_180003106
0x1800030fe  test    edi, edi
0x180003100  jz      loc_1800032BB
0x180003106  mov     r9, r13; ArgList
0x180003109  lea     rcx, [rbp+3C0h+Buffer]; Buffer
0x18000310d  mov     r13d, 3FFh
0x180003113  mov     r8, r12; Format
0x180003116  mov     edx, r13d; BufferCount
0x180003119  call    _vsnprintf
0x18000311e  xor     r12d, r12d
0x180003121  test    eax, eax
0x180003123  js      short loc_18000312A
0x180003125  cmp     eax, r13d
0x180003128  jb      short loc_180003131
0x18000312a  mov     [rbp+3C0h+var_41], r12b
0x180003131  test    edi, edi
0x180003133  jz      loc_180003288
0x180003139  test    esi, esi
0x18000313b  jnz     loc_1800031F3
0x180003141  lea     r9, [rbp+3C0h+Buffer]; char *
0x180003145  mov     r8d, r15d; int
0x180003148  mov     rdx, r14; char *
0x18000314b  xor     ecx, ecx; int
0x18000314d  call    ?UnderErrorUploadLimit@@YAHHPEBDH0@Z; UnderErrorUploadLimit(int,char const *,int,char const *)
0x180003152  test    eax, eax
0x180003154  jz      loc_180003288
0x18000315a  mov     eax, cs:dword_180007000
0x180003160  cmp     eax, 5
0x180003163  jbe     loc_180003288
0x180003169  mov     rdx, cs:qword_180007018
0x180003170  mov     rcx, 400000000000h
0x18000317a  mov     rax, cs:qword_180007010
0x180003181  test    rcx, rax
0x180003184  jz      loc_180003288
0x18000318a  mov     rax, rdx
0x18000318d  and     rax, rcx
0x180003190  cmp     rax, rdx
0x180003193  jnz     loc_180003288
0x180003199  lea     rax, [rbp+3C0h+Buffer]
0x18000319d  mov     [rsp+4C0h+var_460], 3000000h
0x1800031a6  mov     [rsp+4C0h+var_458], rax
0x1800031ab  lea     rdx, byte_180005B09
0x1800031b2  lea     rax, [rsp+4C0h+var_460]
0x1800031b7  mov     [rsp+4C0h+var_470], r15d
0x1800031bc  mov     [rsp+4C0h+var_480], rax
0x1800031c1  lea     rax, [rsp+4C0h+var_458]
0x1800031c6  mov     [rsp+4C0h+var_488], rax
0x1800031cb  lea     rax, [rsp+4C0h+var_470]
0x1800031d0  mov     [rsp+4C0h+var_490], rax
0x1800031d5  lea     rax, [rsp+4C0h+var_450]
0x1800031da  mov     [rsp+4C0h+var_498], rax
0x1800031df  lea     rax, [rsp+4C0h+var_46C]
0x1800031e4  mov     [rsp+4C0h+var_450], r14
0x1800031e9  mov     [rsp+4C0h+var_46C], r12d
0x1800031ee  jmp     loc_18000327E
0x1800031f3  mov     eax, cs:dword_180007000
0x1800031f9  cmp     eax, 5
0x1800031fc  jbe     loc_180003288
0x180003202  mov     rdx, cs:qword_180007018
0x180003209  mov     rcx, 400000000000h
0x180003213  mov     rax, cs:qword_180007010
0x18000321a  test    rcx, rax
0x18000321d  jz      short loc_180003288
0x18000321f  mov     rax, rdx
0x180003222  and     rax, rcx
0x180003225  cmp     rax, rdx
0x180003228  jnz     short loc_180003288
0x18000322a  lea     rax, [rbp+3C0h+Buffer]
0x18000322e  mov     [rsp+4C0h+var_450], 2000000h
0x180003237  mov     [rsp+4C0h+var_458], rax
0x18000323c  lea     rdx, byte_180005AB9
0x180003243  lea     rax, [rsp+4C0h+var_450]
0x180003248  mov     [rsp+4C0h+var_46C], r15d
0x18000324d  mov     [rsp+4C0h+var_480], rax
0x180003252  lea     rax, [rsp+4C0h+var_458]
0x180003257  mov     [rsp+4C0h+var_488], rax
0x18000325c  lea     rax, [rsp+4C0h+var_46C]
0x180003261  mov     [rsp+4C0h+var_490], rax
0x180003266  lea     rax, [rsp+4C0h+var_460]
0x18000326b  mov     [rsp+4C0h+var_498], rax
0x180003270  lea     rax, [rsp+4C0h+var_470]
0x180003275  mov     [rsp+4C0h+var_460], r14
0x18000327a  mov     [rsp+4C0h+var_470], esi
0x18000327e  mov     [rsp+4C0h+var_4A0], rax
0x180003283  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U1@U2@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@34AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x180003288  cmp     [rsp+4C0h+var_468], r12d
0x18000328d  jz      short loc_1800032BB
0x18000328f  mov     rcx, cs:qword_1800072B8
0x180003296  test    rcx, rcx
0x180003299  jz      short loc_1800032BB
0x18000329b  lea     rax, [rbp+3C0h+Buffer]
0x18000329f  mov     r9d, r15d
0x1800032a2  mov     [rsp+4C0h+var_498], rax
0x1800032a7  mov     r8, r14
0x1800032aa  mov     rax, [rsp+4C0h+var_448]
0x1800032af  mov     edx, esi
0x1800032b1  mov     [rsp+4C0h+var_4A0], rax
0x1800032b6  call    ?Trace@ZTracer@@QEAAXW4ZTraceLevel@@PEBDHPEBX1@Z; ZTracer::Trace(ZTraceLevel,char const *,int,void const *,char const *)
0x1800032bb  mov     ecx, ebx; dwErrCode
0x1800032bd  call    cs:__imp_SetLastError
0x1800032c3  mov     rcx, [rbp+3C0h+var_40]
0x1800032ca  xor     rcx, rsp; StackCookie
0x1800032cd  call    __security_check_cookie
0x1800032d2  mov     rbx, [rsp+4C0h+arg_0]
0x1800032da  add     rsp, 490h
0x1800032e1  pop     r15
0x1800032e3  pop     r14
0x1800032e5  pop     r13
0x1800032e7  pop     r12
0x1800032e9  pop     rdi
0x1800032ea  pop     rsi
0x1800032eb  pop     rbp
0x1800032ec  retn
```
