# SingleObjectWaiter::Wait(ObjectHandle &,ulong)

- ea: `0x18001f748`
- end: `0x18001f981`
- name: `?Wait@SingleObjectWaiter@@QEAAXAEAVObjectHandle@@K@Z`
- size: `569`
- prototype: `void __fastcall(SingleObjectWaiter *__hidden this, struct ObjectHandle *, unsigned int)`
- caller_count: `6`
- callee_count: `12`
- tags: `loader_planting`

## callers

- `0x18009d330`
- `0x1800a1070`
- `0x1800eaa3c`
- `0x180104b14`
- `0x180104b8c`
- `0x180120ba4`

## callees

- `0x1800024a4`
- `0x180004510`
- `0x180004874`
- `0x1800082d0`
- `0x180008310`
- `0x18000fac0`
- `0x180011798`
- `0x180018be0`
- `0x180018d3c`
- `0x18001f0ac`
- `0x18001f130`
- `0x18001f748`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f80d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f80d`
- `ntdll!EtwEventActivityIdControl` at `0x18001f769`
- `ntdll!EtwEventActivityIdControl` at `0x18001f769`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18001f7d8`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18001f7d8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18001f894`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18001f917`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18001f894`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18001f917`

## string_xrefs

- `0x18001f836`: `SingleObjectWaiter - CreateThreadpoolWork`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall SingleObjectWaiter::Wait(SingleObjectWaiter *this, struct ObjectHandle *a2, unsigned int a3)
{
  __int64 v3; // rsi
  bool v5; // dl
  struct _TP_CALLBACK_ENVIRON_V3 *v6; // r8
  __int64 v7; // rdx
  __int64 v8; // r9
  PTP_WAIT ThreadpoolWait; // rax
  DWORD LastError; // eax
  CHostedCacheMsgEncoding *v11; // rcx
  __int64 v12; // rdx
  _QWORD *v13; // rax
  __int64 v14; // [rsp+30h] [rbp-38h] BYREF
  char v15; // [rsp+38h] [rbp-30h]
  _BYTE v16[40]; // [rsp+40h] [rbp-28h] BYREF

  v3 = a3;
  EtwEventActivityIdControl(1, (char *)this + 8);
  ObjectHandle::operator=((SingleObjectWaiter *)((char *)this + 56));
  InCritSec::InCritSec((InCritSec *)v16, (SingleObjectWaiter *)((char *)this + 88), 1);
  if ( *((_QWORD *)this + 6) )
    SingleObjectWaiter::Cancel(this, v5);
  v6 = 0;
  v14 = 0;
  v15 = 0;
  v7 = *((_QWORD *)this + 5);
  if ( !v7 )
  {
LABEL_6:
    ThreadpoolWait = CreateThreadpoolWait(SingleObjectWaiter::WaitCallback, this, v6);
    *((_QWORD *)this + 6) = ThreadpoolWait;
    if ( !ThreadpoolWait )
    {
      if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800000) != 0 )
      {
        if ( *((_BYTE *)WPP_GLOBAL_Control + 105) )
        {
          LastError = GetLastError();
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 12),
            12,
            WPP_7e3fc60a412935a0e7501bc6f541d1b0_Traceguids,
            this,
            LastError);
        }
      }
      SystemError::Throw(L"SingleObjectWaiter - CreateThreadpoolWork");
    }
    if ( (_DWORD)v3 == -1 )
    {
      std::auto_ptr<unsigned short>::reset((char *)this + 72, 0);
      SetThreadpoolWait(*((PTP_WAIT *)this + 6), *((HANDLE *)this + 8), *((PFILETIME *)this + 9));
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
      {
        v12 = 13;
        goto LABEL_21;
      }
    }
    else
    {
      v13 = operator new(8u);
      *v13 = -10000 * v3;
      std::auto_ptr<unsigned short>::reset((char *)this + 72, v13);
      SetThreadpoolWait(*((PTP_WAIT *)this + 6), *((HANDLE *)this + 8), *((PFILETIME *)this + 9));
      if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
      {
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 12), 14, WPP_7e3fc60a412935a0e7501bc6f541d1b0_Traceguids, this, v3);
      }
    }
    goto LABEL_26;
  }
  LockSentry<ReadersWriterLock,1>::Attach(&v14, v7 + 104, 0);
  v8 = *((_QWORD *)this + 5);
  if ( !*(_BYTE *)(v8 + 88) )
  {
    v6 = (struct _TP_CALLBACK_ENVIRON_V3 *)(v8 + 16);
    goto LABEL_6;
  }
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
  {
    v12 = 15;
LABEL_21:
    WPP_SF_q(*((_QWORD *)v11 + 12), v12, WPP_7e3fc60a412935a0e7501bc6f541d1b0_Traceguids);
  }
LABEL_26:
  LockSentry<ReadersWriterLock,1>::Unlock(&v14);
  InCritSec::~InCritSec((InCritSec *)v16);
}

```

## disassembly

```asm
0x18001f748  mov     [rsp+arg_0], rbx
0x18001f74d  mov     [rsp+arg_8], rsi
0x18001f752  push    rdi
0x18001f753  sub     rsp, 60h
0x18001f757  mov     esi, r8d
0x18001f75a  mov     rbx, rdx
0x18001f75d  mov     rdi, rcx
0x18001f760  lea     rdx, [rcx+8]
0x18001f764  mov     ecx, 1
0x18001f769  call    cs:__imp_EtwEventActivityIdControl
0x18001f76f  lea     rcx, [rdi+38h]; this
0x18001f773  mov     rdx, rbx
0x18001f776  call    ??4ObjectHandle@@QEAAAEAV0@AEBV0@@Z; ObjectHandle::operator=(ObjectHandle const &)
0x18001f77b  lea     rdx, [rdi+58h]; struct CritSec *
0x18001f77f  mov     r8b, 1; bool
0x18001f782  lea     rcx, [rsp+68h+var_28]; this
0x18001f787  call    ??0InCritSec@@QEAA@AEAVCritSec@@_N@Z; InCritSec::InCritSec(CritSec &,bool)
0x18001f78c  nop
0x18001f78d  xor     ebx, ebx
0x18001f78f  cmp     [rdi+30h], rbx
0x18001f793  jz      short loc_18001F79D
0x18001f795  mov     rcx, rdi; this
0x18001f798  call    ?Cancel@SingleObjectWaiter@@QEAAX_N@Z; SingleObjectWaiter::Cancel(bool)
0x18001f79d  mov     r8, rbx
0x18001f7a0  mov     [rsp+68h+var_38], rbx
0x18001f7a5  mov     [rsp+68h+var_30], bl
0x18001f7a9  mov     rdx, [rdi+28h]
0x18001f7ad  test    rdx, rdx
0x18001f7b0  jz      short loc_18001F7CE
0x18001f7b2  add     rdx, 68h ; 'h'
0x18001f7b6  lea     rcx, [rsp+68h+var_38]
0x18001f7bb  call    ?Attach@?$LockSentry@VReadersWriterLock@@$00@@QEAAXAEAVReadersWriterLock@@_N@Z; LockSentry<ReadersWriterLock,1>::Attach(ReadersWriterLock &,bool)
0x18001f7c0  mov     r9, [rdi+28h]
0x18001f7c4  cmp     [r9+58h], bl
0x18001f7c8  jnz     short loc_18001F843
0x18001f7ca  lea     r8, [r9+10h]; pcbe
0x18001f7ce  mov     rdx, rdi; pv
0x18001f7d1  lea     rcx, ?WaitCallback@SingleObjectWaiter@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x18001f7d8  call    cs:__imp_CreateThreadpoolWait
0x18001f7de  mov     [rdi+30h], rax
0x18001f7e2  test    rax, rax
0x18001f7e5  jnz     loc_18001F878
0x18001f7eb  lea     rax, WPP_GLOBAL_Control
0x18001f7f2  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f7f9  cmp     rcx, rax
0x18001f7fc  jz      short loc_18001F836
0x18001f7fe  test    dword ptr [rcx+6Ch], 800000h
0x18001f805  jz      short loc_18001F836
0x18001f807  cmp     byte ptr [rcx+69h], 1
0x18001f80b  jb      short loc_18001F836
0x18001f80d  call    cs:__imp_GetLastError
0x18001f813  mov     edx, 0Ch
0x18001f818  mov     [rsp+68h+var_48], eax
0x18001f81c  mov     r9, rdi
0x18001f81f  lea     r8, WPP_7e3fc60a412935a0e7501bc6f541d1b0_Traceguids
0x18001f826  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f82d  mov     rcx, [rcx+60h]
0x18001f831  call    WPP_SF_qD
0x18001f836  lea     rcx, aSingleobjectwa; "SingleObjectWaiter - CreateThreadpoolWo"...
0x18001f83d  call    ?Throw@SystemError@@SAXPEBG@Z; SystemError::Throw(ushort const *)
0x18001f843  lea     rax, WPP_GLOBAL_Control
0x18001f84a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f851  cmp     rcx, rax
0x18001f854  jz      loc_18001F95C
0x18001f85a  test    dword ptr [rcx+6Ch], 800000h
0x18001f861  jz      loc_18001F95C
0x18001f867  cmp     byte ptr [rcx+69h], 4
0x18001f86b  jb      loc_18001F95C
0x18001f871  mov     edx, 0Fh
0x18001f876  jmp     short loc_18001F8D0
0x18001f878  cmp     esi, 0FFFFFFFFh
0x18001f87b  jnz     short loc_18001F8E2
0x18001f87d  xor     edx, edx
0x18001f87f  lea     rcx, [rdi+48h]
0x18001f883  call    ?reset@?$auto_ptr@G@std@@QEAAXPEAG@Z; std::auto_ptr<ushort>::reset(ushort *)
0x18001f888  mov     r8, [rdi+48h]; pftTimeout
0x18001f88c  mov     rdx, [rdi+40h]; h
0x18001f890  mov     rcx, [rdi+30h]; pwa
0x18001f894  call    cs:__imp_SetThreadpoolWait
0x18001f89a  lea     rax, WPP_GLOBAL_Control
0x18001f8a1  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f8a8  cmp     rcx, rax
0x18001f8ab  jz      loc_18001F95C
0x18001f8b1  test    dword ptr [rcx+6Ch], 800000h
0x18001f8b8  jz      loc_18001F95C
0x18001f8be  cmp     byte ptr [rcx+69h], 4
0x18001f8c2  jb      loc_18001F95C
0x18001f8c8  mov     edx, 0Dh
0x18001f8cd  mov     r9, rdi
0x18001f8d0  lea     r8, WPP_7e3fc60a412935a0e7501bc6f541d1b0_Traceguids
0x18001f8d7  mov     rcx, [rcx+60h]
0x18001f8db  call    WPP_SF_q
0x18001f8e0  jmp     short loc_18001F95C
0x18001f8e2  mov     ecx, 8; Size
0x18001f8e7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001f8ec  mov     rdx, rax
0x18001f8ef  imul    rax, rsi, 0FFFFFFFFFFFFD8F0h
0x18001f8f6  mov     rcx, rax
0x18001f8f9  shr     rcx, 20h
0x18001f8fd  mov     [rdx+4], ecx
0x18001f900  mov     [rdx], eax
0x18001f902  lea     rcx, [rdi+48h]
0x18001f906  call    ?reset@?$auto_ptr@G@std@@QEAAXPEAG@Z; std::auto_ptr<ushort>::reset(ushort *)
0x18001f90b  mov     r8, [rdi+48h]; pftTimeout
0x18001f90f  mov     rdx, [rdi+40h]; h
0x18001f913  mov     rcx, [rdi+30h]; pwa
0x18001f917  call    cs:__imp_SetThreadpoolWait
0x18001f91d  lea     rax, WPP_GLOBAL_Control
0x18001f924  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f92b  cmp     rcx, rax
0x18001f92e  jz      short loc_18001F95C
0x18001f930  test    dword ptr [rcx+6Ch], 800000h
0x18001f937  jz      short loc_18001F95C
0x18001f939  cmp     byte ptr [rcx+69h], 4
0x18001f93d  jb      short loc_18001F95C
0x18001f93f  mov     edx, 0Eh
0x18001f944  mov     [rsp+68h+var_48], esi
0x18001f948  mov     r9, rdi
0x18001f94b  lea     r8, WPP_7e3fc60a412935a0e7501bc6f541d1b0_Traceguids
0x18001f952  mov     rcx, [rcx+60h]
0x18001f956  call    WPP_SF_qD
0x18001f95b  nop
0x18001f95c  lea     rcx, [rsp+68h+var_38]
0x18001f961  call    ?Unlock@?$LockSentry@VReadersWriterLock@@$00@@QEAAXXZ; LockSentry<ReadersWriterLock,1>::Unlock(void)
0x18001f966  nop
0x18001f967  lea     rcx, [rsp+68h+var_28]; this
0x18001f96c  call    ??1InCritSec@@QEAA@XZ; InCritSec::~InCritSec(void)
0x18001f971  mov     rbx, [rsp+68h+arg_0]
0x18001f976  mov     rsi, [rsp+68h+arg_8]
0x18001f97b  add     rsp, 60h
0x18001f97f  pop     rdi
0x18001f980  retn
```
