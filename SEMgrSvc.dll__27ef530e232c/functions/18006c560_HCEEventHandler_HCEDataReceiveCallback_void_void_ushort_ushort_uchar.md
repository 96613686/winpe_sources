# HCEEventHandler::HCEDataReceiveCallback(void *,void *,ushort,ushort,uchar *)

- ea: `0x18006c560`
- end: `0x18006c68a`
- name: `?HCEDataReceiveCallback@HCEEventHandler@@CAXPEAX0GGPEAE@Z`
- size: `298`
- prototype: `void __usercall(HCEEventHandler *this@<rcx>, void *@<rdx>, unsigned __int16@<r8w>, unsigned __int16@<r9w>, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180001008`
- `0x18006c28c`
- `0x18006c560`
- `0x18006d030`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006c5e9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006c66f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006c5e9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006c66f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006c590`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006c590`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18006c5b6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18006c665`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18006c5b6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18006c665`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall HCEEventHandler::HCEDataReceiveCallback(
        PTP_WAIT *this,
        void *a2,
        unsigned __int16 a3,
        unsigned __int16 a4,
        unsigned __int8 *a5)
{
  struct _RTL_CRITICAL_SECTION *v8; // rdi
  int v9; // esi
  int v10; // r8d
  int v11; // r9d
  const char *v12; // [rsp+40h] [rbp-38h] BYREF
  const char *v13; // [rsp+48h] [rbp-30h] BYREF
  char v14; // [rsp+50h] [rbp-28h]
  HANDLE h; // [rsp+80h] [rbp+8h] BYREF

  h = 0;
  v8 = (struct _RTL_CRITICAL_SECTION *)(this + 1);
  v13 = (const char *)(this + 1);
  EnterCriticalSection((LPCRITICAL_SECTION)(this + 1));
  v14 = 1;
  if ( *((_WORD *)this + 85) )
  {
    HCEEventHandler::ClearPendingApdu((HCEEventHandler *)this);
    SetThreadpoolWait(this[12], 0, 0);
  }
  v9 = HCEEventHandler::ProcessReceive((HCEEventHandler *)this, a3, a5, a4, &h);
  if ( v9 >= 0 )
  {
    if ( h && *((_BYTE *)this + 200) )
      SetThreadpoolWait(this[12], h, 0);
    LeaveCriticalSection(v8);
  }
  else
  {
    LeaveCriticalSection(v8);
    if ( (unsigned int)dword_18012F048 > 2 )
    {
      LODWORD(h) = v9;
      v12 = "Failed to process a SE event.";
      v13 = "HCEEventHandler::HCEDataReceiveCallback";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        dword_18012F048,
        (unsigned int)byte_18011D021,
        v10,
        v11,
        (__int64)&v13,
        (__int64)&v12,
        (__int64)&h);
    }
  }
}

```

## disassembly

```asm
0x18006c560  mov     rax, rsp
0x18006c563  mov     [rax+10h], rbx
0x18006c567  mov     [rax+18h], rbp
0x18006c56b  push    rsi
0x18006c56c  push    rdi
0x18006c56d  push    r14
0x18006c56f  sub     rsp, 60h
0x18006c573  movzx   esi, r9w
0x18006c577  movzx   ebp, r8w
0x18006c57b  mov     rbx, rcx
0x18006c57e  xor     r14d, r14d
0x18006c581  mov     [rax+8], r14
0x18006c585  lea     rdi, [rcx+8]
0x18006c589  mov     [rax-30h], rdi
0x18006c58d  mov     rcx, rdi; lpCriticalSection
0x18006c590  call    cs:__imp_EnterCriticalSection
0x18006c596  mov     [rsp+78h+var_28], 1
0x18006c59b  cmp     [rbx+0AAh], r14w
0x18006c5a3  jz      short loc_18006C5BC
0x18006c5a5  mov     rcx, rbx; this
0x18006c5a8  call    ?ClearPendingApdu@HCEEventHandler@@AEAAXXZ; HCEEventHandler::ClearPendingApdu(void)
0x18006c5ad  xor     r8d, r8d; pftTimeout
0x18006c5b0  xor     edx, edx; h
0x18006c5b2  mov     rcx, [rbx+60h]; pwa
0x18006c5b6  call    cs:__imp_SetThreadpoolWait
0x18006c5bc  lea     rax, [rsp+78h+h]
0x18006c5c4  mov     [rsp+78h+var_58], rax; void **
0x18006c5c9  movzx   r9d, si; unsigned __int16
0x18006c5cd  mov     r8, [rsp+78h+arg_20]; unsigned __int8 *
0x18006c5d5  movzx   edx, bp; unsigned __int16
0x18006c5d8  mov     rcx, rbx; this
0x18006c5db  call    ?ProcessReceive@HCEEventHandler@@QEAAJGPEAEGPEAPEAX@Z; HCEEventHandler::ProcessReceive(ushort,uchar *,ushort,void * *)
0x18006c5e0  mov     esi, eax
0x18006c5e2  test    eax, eax
0x18006c5e4  jns     short loc_18006C648
0x18006c5e6  mov     rcx, rdi; lpCriticalSection
0x18006c5e9  call    cs:__imp_LeaveCriticalSection
0x18006c5ef  mov     ecx, cs:dword_18012F048
0x18006c5f5  cmp     ecx, 2
0x18006c5f8  jbe     short loc_18006C675
0x18006c5fa  mov     dword ptr [rsp+78h+h], esi
0x18006c601  lea     rax, aFailedToProces; "Failed to process a SE event."
0x18006c608  mov     [rsp+78h+var_38], rax
0x18006c60d  lea     rax, aHceeventhandle; "HCEEventHandler::HCEDataReceiveCallback"
0x18006c614  mov     [rsp+78h+var_30], rax
0x18006c619  lea     rax, [rsp+78h+h]
0x18006c621  mov     [rsp+78h+var_48], rax
0x18006c626  lea     rax, [rsp+78h+var_38]
0x18006c62b  mov     [rsp+78h+var_50], rax
0x18006c630  lea     rax, [rsp+78h+var_30]
0x18006c635  mov     [rsp+78h+var_58], rax
0x18006c63a  lea     rdx, byte_18011D021
0x18006c641  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18006c646  jmp     short loc_18006C675
0x18006c648  mov     rdx, [rsp+78h+h]; h
0x18006c650  test    rdx, rdx
0x18006c653  jz      short loc_18006C66C
0x18006c655  cmp     [rbx+0C8h], r14b
0x18006c65c  jz      short loc_18006C66C
0x18006c65e  xor     r8d, r8d; pftTimeout
0x18006c661  mov     rcx, [rbx+60h]; pwa
0x18006c665  call    cs:__imp_SetThreadpoolWait
0x18006c66b  nop
0x18006c66c  mov     rcx, rdi; lpCriticalSection
0x18006c66f  call    cs:__imp_LeaveCriticalSection
0x18006c675  lea     r11, [rsp+78h+var_18]
0x18006c67a  mov     rbx, [r11+28h]
0x18006c67e  mov     rbp, [r11+30h]
0x18006c682  mov     rsp, r11
0x18006c685  pop     r14
0x18006c687  pop     rdi
0x18006c688  pop     rsi
0x18006c689  retn
```
