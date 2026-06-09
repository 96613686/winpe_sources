# CReaderDriver::Initialize(void)

- ea: `0x18002d0c0`
- end: `0x18002d34b`
- name: `?Initialize@CReaderDriver@@UEAAXXZ`
- size: `651`
- prototype: `void __fastcall(CReaderDriver *__hidden this)`
- caller_count: `0`
- callee_count: `11`
- tags: ``

## callees

- `0x1800016c0`
- `0x1800022b0`
- `0x180006700`
- `0x18000f770`
- `0x180014180`
- `0x180018658`
- `0x180029284`
- `0x18002d0c0`
- `0x18002d870`
- `0x18002edb0`
- `0x18003261b`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002d0e3`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002d1f6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002d0e3`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002d1f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d108`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d214`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d2bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d334`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d108`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d214`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d2bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d334`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18002d29f`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18002d29f`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18002d329`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18002d329`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CReaderDriver::Initialize(CReaderDriver *this)
{
  CReaderDriver *v1; // rbx
  char *EventW; // rsi
  DWORD LastError; // eax
  int IsValid; // eax
  const unsigned __int8 *v5; // rcx
  int v6; // ebx
  unsigned int v7; // r8d
  const unsigned __int16 *v8; // rdx
  char *v9; // rsi
  DWORD v10; // eax
  const unsigned __int8 *v11; // rcx
  int v12; // ebx
  char *Thread; // rsi
  DWORD v14; // eax
  const unsigned __int8 *v15; // rcx
  int v16; // ebx
  int pExceptionObject; // [rsp+30h] [rbp-28h] BYREF
  int v18; // [rsp+34h] [rbp-24h] BYREF
  int v19; // [rsp+38h] [rbp-20h] BYREF
  CReader *v20[3]; // [rsp+40h] [rbp-18h] BYREF

  v1 = this;
  EventW = (char *)CreateEventW(0, 1, 0, 0);
  *((_QWORD *)v1 + 110) = EventW;
  if ( (unsigned __int64)(EventW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    LastError = GetLastError();
  else
    LastError = 0;
  *((_DWORD *)v1 + 224) = LastError;
  if ( (unsigned int)CHandleObject::IsValid((CReaderDriver *)((char *)v1 + 888)) )
    CHandleObject::Close((void **)v1 + 111);
  *((_QWORD *)v1 + 111) = EventW;
  IsValid = CHandleObject::IsValid((CReaderDriver *)((char *)v1 + 888));
  try
  {
    if ( !IsValid )
    {
      v6 = *((_DWORD *)v1 + 224);
      CalaisError(v5, 0x25Du, v6, 0, 0, 0);
      pExceptionObject = v6;
      throw (ulong *)&pExceptionObject;
    }
    try
    {
      CLatchReader::CLatchReader((CLatchReader *)v20, v1, 0);
      *((_DWORD *)v1 + 8) = CReader::GetReaderAttr(v1, 393552, v7);
      CLatchReader::~CLatchReader(v20);
    }
    catch ( ... )
    {
      *((_DWORD *)this + 8) = 2;
      v1 = this;
    }
    CReader::Initialize(v1);
    if ( (*((_DWORD *)v1 + 9) & 1) != 0 )
      AppRegisterDevice(*((void **)v1 + 104), v8, (void **)v1 + 106);
    if ( *((_DWORD *)v1 + 10) == 256 )
      CPowerSupport::AddReader((unsigned int *)v1 + 184, (void **)v1 + 93, (void **)v1 + 94);
    v9 = (char *)CreateEventW(0, 1, 0, 0);
    if ( (unsigned __int64)(v9 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
      v10 = GetLastError();
    else
      v10 = 0;
    *((_DWORD *)v1 + 228) = v10;
    if ( (unsigned int)CHandleObject::IsValid((CReaderDriver *)((char *)v1 + 904)) )
      CHandleObject::Close((void **)v1 + 113);
    *((_QWORD *)v1 + 113) = v9;
    if ( !(unsigned int)CHandleObject::IsValid((CReaderDriver *)((char *)v1 + 904)) )
    {
      v12 = *((_DWORD *)v1 + 228);
      CalaisError(v11, 0x25Eu, v12, 0, 0, 0);
      v18 = v12;
      throw (ulong *)&v18;
    }
    Thread = (char *)CreateThread(0, 0, MonitorReader, v1, 4u, (LPDWORD)v1 + 194);
    if ( (unsigned __int64)(Thread - 1) > 0xFFFFFFFFFFFFFFFDuLL )
      v14 = GetLastError();
    else
      v14 = 0;
    *((_DWORD *)v1 + 192) = v14;
    if ( (unsigned int)CHandleObject::IsValid((CReaderDriver *)((char *)v1 + 760)) )
      CHandleObject::Close((void **)v1 + 95);
    *((_QWORD *)v1 + 95) = Thread;
    if ( !(unsigned int)CHandleObject::IsValid((CReaderDriver *)((char *)v1 + 760)) )
    {
      v16 = *((_DWORD *)v1 + 192);
      CalaisError(v15, 0x25Fu, v16, 0, 0, 0);
      v19 = v16;
      throw (ulong *)&v19;
    }
    if ( ResumeThread(Thread) == -1 )
      GetLastError();
  }
  catch ( ... )
  {
    (*(void (__fastcall **)(CReaderDriver *))(*(_QWORD *)this + 16LL))(this);
    throw;
  }
}

```

## disassembly

```asm
0x18002d0c0  mov     [rsp+arg_8], rbx
0x18002d0c5  mov     [rsp+arg_10], rsi
0x18002d0ca  mov     [rsp+arg_0], rcx
0x18002d0cf  push    rdi
0x18002d0d0  sub     rsp, 50h
0x18002d0d4  mov     rbx, rcx
0x18002d0d7  xor     r9d, r9d; lpName
0x18002d0da  xor     r8d, r8d; bInitialState
0x18002d0dd  lea     edx, [r9+1]; bManualReset
0x18002d0e1  xor     ecx, ecx; lpEventAttributes
0x18002d0e3  call    cs:__imp_CreateEventW
0x18002d0e9  mov     rsi, rax
0x18002d0ec  mov     [rbx+370h], rax
0x18002d0f3  lea     rdi, [rbx+378h]
0x18002d0fa  lea     rcx, [rax-1]
0x18002d0fe  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18002d102  ja      short loc_18002D108
0x18002d104  xor     eax, eax
0x18002d106  jmp     short loc_18002D10E
0x18002d108  call    cs:__imp_GetLastError
0x18002d10e  mov     [rdi+8], eax
0x18002d111  mov     rcx, rdi; this
0x18002d114  call    ?IsValid@CHandleObject@@QEBAHXZ; CHandleObject::IsValid(void)
0x18002d119  test    eax, eax
0x18002d11b  jz      short loc_18002D125
0x18002d11d  mov     rcx, rdi; this
0x18002d120  call    ?Close@CHandleObject@@QEAAKXZ; CHandleObject::Close(void)
0x18002d125  mov     [rdi], rsi
0x18002d128  mov     rcx, rdi; this
0x18002d12b  call    ?IsValid@CHandleObject@@QEBAHXZ; CHandleObject::IsValid(void)
0x18002d130  test    eax, eax
0x18002d132  jnz     short loc_18002D172
0x18002d134  mov     ebx, [rbx+380h]
0x18002d13a  mov     [rsp+58h+lpThreadId], 0; unsigned __int16 *
0x18002d143  mov     qword ptr [rsp+58h+dwCreationFlags], 0; unsigned __int16 *
0x18002d14c  xor     r9d, r9d; unsigned __int16 *
0x18002d14f  mov     r8d, ebx; unsigned int
0x18002d152  mov     edx, 25Dh; unsigned int
0x18002d157  call    ?CalaisError@@YAXPEBEKKPEBG11@Z; CalaisError(uchar const *,ulong,ulong,ushort const *,ushort const *,ushort const *)
0x18002d15c  mov     [rsp+58h+pExceptionObject], ebx
0x18002d160  lea     rdx, _TI1K; pThrowInfo
0x18002d167  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x18002d16c  call    _CxxThrowException_0
0x18002d172  xor     r8d, r8d; struct CReader::ActiveState *
0x18002d175  mov     rdx, rbx; struct CReader *
0x18002d178  lea     rcx, [rsp+58h+var_18]; this
0x18002d17d  call    ??0CLatchReader@@QEAA@PEAVCReader@@PEBUActiveState@1@@Z; CLatchReader::CLatchReader(CReader *,CReader::ActiveState const *)
0x18002d182  nop
0x18002d183  mov     edx, 60150h; unsigned int
0x18002d188  mov     rcx, rbx; this
0x18002d18b  call    ?GetReaderAttr@CReader@@QEAAKKH@Z; CReader::GetReaderAttr(ulong,int)
0x18002d190  mov     [rbx+20h], eax
0x18002d193  lea     rcx, [rsp+58h+var_18]; this
0x18002d198  call    ??1CLatchReader@@QEAA@XZ; CLatchReader::~CLatchReader(void)
0x18002d19d  nop
0x18002d19e  jmp     short loc_18002D1A5
0x18002d1a0  mov     rbx, [rsp+58h+arg_0]
0x18002d1a5  mov     rcx, rbx; this
0x18002d1a8  call    ?Initialize@CReader@@UEAAXXZ; CReader::Initialize(void)
0x18002d1ad  mov     eax, [rbx+24h]
0x18002d1b0  test    al, 1
0x18002d1b2  jz      short loc_18002D1C7
0x18002d1b4  lea     r8, [rbx+350h]; void **
0x18002d1bb  mov     rcx, [rbx+340h]; void *
0x18002d1c2  call    ?AppRegisterDevice@@YAXPEAXPEBGPEAPEAX@Z; AppRegisterDevice(void *,ushort const *,void * *)
0x18002d1c7  cmp     dword ptr [rbx+28h], 100h
0x18002d1ce  jnz     short loc_18002D1EA
0x18002d1d0  lea     r8, [rbx+2F0h]; void **
0x18002d1d7  lea     rdx, [rbx+2E8h]; void **
0x18002d1de  lea     rcx, [rbx+2E0h]; unsigned int *
0x18002d1e5  call    ?AddReader@CPowerSupport@@SAKPEAKPEAPEAX1@Z; CPowerSupport::AddReader(ulong *,void * *,void * *)
0x18002d1ea  xor     r9d, r9d; lpName
0x18002d1ed  xor     r8d, r8d; bInitialState
0x18002d1f0  lea     edx, [r9+1]; bManualReset
0x18002d1f4  xor     ecx, ecx; lpEventAttributes
0x18002d1f6  call    cs:__imp_CreateEventW
0x18002d1fc  mov     rsi, rax
0x18002d1ff  lea     rdi, [rbx+388h]
0x18002d206  lea     rcx, [rax-1]
0x18002d20a  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18002d20e  ja      short loc_18002D214
0x18002d210  xor     eax, eax
0x18002d212  jmp     short loc_18002D21A
0x18002d214  call    cs:__imp_GetLastError
0x18002d21a  mov     [rdi+8], eax
0x18002d21d  mov     rcx, rdi; this
0x18002d220  call    ?IsValid@CHandleObject@@QEBAHXZ; CHandleObject::IsValid(void)
0x18002d225  test    eax, eax
0x18002d227  jz      short loc_18002D231
0x18002d229  mov     rcx, rdi; this
0x18002d22c  call    ?Close@CHandleObject@@QEAAKXZ; CHandleObject::Close(void)
0x18002d231  mov     [rdi], rsi
0x18002d234  mov     rcx, rdi; this
0x18002d237  call    ?IsValid@CHandleObject@@QEBAHXZ; CHandleObject::IsValid(void)
0x18002d23c  test    eax, eax
0x18002d23e  jnz     short loc_18002D27D
0x18002d240  mov     ebx, [rbx+390h]
0x18002d246  mov     [rsp+58h+lpThreadId], 0; unsigned __int16 *
0x18002d24f  mov     qword ptr [rsp+58h+dwCreationFlags], 0; unsigned __int16 *
0x18002d258  xor     r9d, r9d; unsigned __int16 *
0x18002d25b  mov     r8d, ebx; unsigned int
0x18002d25e  mov     edx, 25Eh; unsigned int
0x18002d263  call    ?CalaisError@@YAXPEBEKKPEBG11@Z; CalaisError(uchar const *,ulong,ulong,ushort const *,ushort const *,ushort const *)
0x18002d268  mov     [rsp+58h+var_24], ebx
0x18002d26c  lea     rdx, _TI1K; pThrowInfo
0x18002d273  lea     rcx, [rsp+58h+var_24]; pExceptionObject
0x18002d278  call    _CxxThrowException_0
0x18002d27d  lea     rax, [rbx+308h]
0x18002d284  mov     [rsp+58h+lpThreadId], rax; lpThreadId
0x18002d289  mov     [rsp+58h+dwCreationFlags], 4; dwCreationFlags
0x18002d291  mov     r9, rbx; lpParameter
0x18002d294  lea     r8, MonitorReader; lpStartAddress
0x18002d29b  xor     edx, edx; dwStackSize
0x18002d29d  xor     ecx, ecx; lpThreadAttributes
0x18002d29f  call    cs:__imp_CreateThread
0x18002d2a5  mov     rsi, rax
0x18002d2a8  lea     rdi, [rbx+2F8h]
0x18002d2af  lea     rcx, [rax-1]
0x18002d2b3  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18002d2b7  ja      short loc_18002D2BD
0x18002d2b9  xor     eax, eax
0x18002d2bb  jmp     short loc_18002D2C3
0x18002d2bd  call    cs:__imp_GetLastError
0x18002d2c3  mov     [rdi+8], eax
0x18002d2c6  mov     rcx, rdi; this
0x18002d2c9  call    ?IsValid@CHandleObject@@QEBAHXZ; CHandleObject::IsValid(void)
0x18002d2ce  test    eax, eax
0x18002d2d0  jz      short loc_18002D2DA
0x18002d2d2  mov     rcx, rdi; this
0x18002d2d5  call    ?Close@CHandleObject@@QEAAKXZ; CHandleObject::Close(void)
0x18002d2da  mov     [rdi], rsi
0x18002d2dd  mov     rcx, rdi; this
0x18002d2e0  call    ?IsValid@CHandleObject@@QEBAHXZ; CHandleObject::IsValid(void)
0x18002d2e5  test    eax, eax
0x18002d2e7  jnz     short loc_18002D326
0x18002d2e9  mov     ebx, [rbx+300h]
0x18002d2ef  mov     [rsp+58h+lpThreadId], 0; unsigned __int16 *
0x18002d2f8  mov     qword ptr [rsp+58h+dwCreationFlags], 0; unsigned __int16 *
0x18002d301  xor     r9d, r9d; unsigned __int16 *
0x18002d304  mov     r8d, ebx; unsigned int
0x18002d307  mov     edx, 25Fh; unsigned int
0x18002d30c  call    ?CalaisError@@YAXPEBEKKPEBG11@Z; CalaisError(uchar const *,ulong,ulong,ushort const *,ushort const *,ushort const *)
0x18002d311  mov     [rsp+58h+var_20], ebx
0x18002d315  lea     rdx, _TI1K; pThrowInfo
0x18002d31c  lea     rcx, [rsp+58h+var_20]; pExceptionObject
0x18002d321  call    _CxxThrowException_0
0x18002d326  mov     rcx, rsi; hThread
0x18002d329  call    cs:__imp_ResumeThread
0x18002d32f  cmp     eax, 0FFFFFFFFh
0x18002d332  jnz     short loc_18002D33B
0x18002d334  call    cs:__imp_GetLastError
0x18002d33a  nop
0x18002d33b  mov     rbx, [rsp+58h+arg_8]
0x18002d340  mov     rsi, [rsp+58h+arg_10]
0x18002d345  add     rsp, 50h
0x18002d349  pop     rdi
0x18002d34a  retn
```
