# CVirtualAudioClient::SetClientProperties(AudioClientProperties const *)

- ea: `0x1800210f0`
- end: `0x1800212db`
- name: `?SetClientProperties@CVirtualAudioClient@@UEAAJPEBUAudioClientProperties@@@Z`
- size: `491`
- prototype: `int(CVirtualAudioClient *__hidden this, const struct AudioClientProperties *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800a8eb0`

## callees

- `0x180010a90`
- `0x180020764`
- `0x1800207bc`
- `0x1800210f0`
- `0x1800212f0`
- `0x18008ac99`
- `0x180123010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180021112`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180021112`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002129a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002129a`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800211e6`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800211e6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180021235`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180021235`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002124e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002124e`

## pseudocode

```c
__int64 __fastcall CVirtualAudioClient::SetClientProperties(
        CVirtualAudioClient *this,
        const struct AudioClientProperties *a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // r14
  __int64 v5; // r8
  __int64 v6; // rdx
  unsigned int v7; // ebx
  __int64 v8; // rdx
  int v9; // ecx
  int v10; // eax
  int v11; // esi
  unsigned __int64 v12; // r9
  __int64 v13; // rdx
  int v14; // ebp
  unsigned __int64 v15; // rax
  __int64 v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // r8
  LPVOID v19; // rax
  void *v20; // rcx
  void *v21; // rcx
  int v23[2]; // [rsp+20h] [rbp-48h] BYREF
  char v24; // [rsp+28h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 352);
  *(_QWORD *)v23 = (char *)this + 352;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 352));
  v24 = 1;
  if ( !a2 )
  {
    v6 = 477;
LABEL_30:
    v7 = -2147024809;
    goto LABEL_31;
  }
  if ( a2->eCategory > 0x14u )
  {
    v6 = 478;
    goto LABEL_30;
  }
  if ( !*((_QWORD *)this + 17) )
  {
    v7 = -2004287484;
    v6 = 479;
LABEL_31:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"avcore\\audiocore\\client\\audioclient\\virtualaudioclient.cpp",
      (const char *)v7,
      v23[0]);
    ATL::CCritSecLock::~CCritSecLock((ATL::CCritSecLock *)v23);
    return v7;
  }
  if ( a2->bIsOffload )
  {
    v6 = 480;
    goto LABEL_30;
  }
  v8 = *((unsigned int *)this + 79);
  v9 = dword_1801487F0[a2->eCategory];
  *((_DWORD *)this + 79) = v9;
  if ( v9 == (_DWORD)v8
    || (v10 = CVirtualAudioClient::DefaultAudioDeviceChanged((CVirtualAudioClient *)((char *)this - 8), v8, v5),
        v11 = v10,
        v10 >= 0) )
  {
    v14 = *((_DWORD *)this + 86);
    v11 = (*(__int64 (__fastcall **)(_QWORD, const struct AudioClientProperties *))(**((_QWORD **)this + 17) + 128LL))(
            *((_QWORD *)this + 17),
            a2);
    while ( 1 )
    {
      v15 = (unsigned int)(v11 + 2004287484);
      if ( (unsigned int)v15 > 0x22 )
        break;
      v16 = 0x400000011LL;
      if ( !_bittest64(&v16, v15) || !v14 )
        break;
      if ( v14 < *((_DWORD *)this + 86) )
        Sleep(0x64u);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        (char *)this + 208,
        0);
      v11 = CVirtualAudioClient::DefaultAudioDeviceChanged((CVirtualAudioClient *)((char *)this - 8), v17, v18);
      if ( v11 >= 0 )
        v11 = (*(__int64 (__fastcall **)(_QWORD, const struct AudioClientProperties *))(**((_QWORD **)this + 17) + 128LL))(
                *((_QWORD *)this + 17),
                a2);
      --v14;
    }
    if ( v11 >= 0 )
    {
      v19 = CoTaskMemAlloc(a2->cbSize);
      v20 = (void *)*((_QWORD *)this + 38);
      *((_QWORD *)this + 38) = v19;
      if ( v20 )
        CoTaskMemFree(v20);
      v21 = (void *)*((_QWORD *)this + 38);
      if ( v21 )
      {
        memcpy_0(v21, a2, a2->cbSize);
        ATL::CCritSecLock::~CCritSecLock((ATL::CCritSecLock *)v23);
        return 0;
      }
      v11 = -2147024882;
      v13 = 560;
    }
    else
    {
      v13 = 554;
    }
    v12 = (unsigned int)v11;
  }
  else
  {
    v12 = (unsigned int)v10;
    v13 = 548;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v13,
    (unsigned int)"avcore\\audiocore\\client\\audioclient\\virtualaudioclient.cpp",
    (const char *)v12,
    v23[0]);
  LeaveCriticalSection(v2);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1800210f0  push    rbx
0x1800210f2  push    rbp
0x1800210f3  push    rsi
0x1800210f4  push    rdi
0x1800210f5  push    r14
0x1800210f7  push    r15
0x1800210f9  sub     rsp, 38h
0x1800210fd  lea     r14, [rcx+160h]
0x180021104  mov     rbx, rcx
0x180021107  mov     rcx, r14; lpCriticalSection
0x18002110a  mov     qword ptr [rsp+68h+var_48], r14; int
0x18002110f  mov     rdi, rdx
0x180021112  call    cs:__imp_EnterCriticalSection
0x180021118  mov     [rsp+68h+var_40], 1
0x18002111d  test    rdi, rdi
0x180021120  jnz     short loc_18002112C
0x180021122  mov     edx, 1DDh
0x180021127  jmp     loc_1800212A9
0x18002112c  cmp     dword ptr [rdi+8], 14h
0x180021130  ja      loc_1800212A4
0x180021136  cmp     qword ptr [rbx+88h], 0
0x18002113e  jnz     short loc_18002114F
0x180021140  mov     ebx, 88890004h
0x180021145  mov     edx, 1DFh
0x18002114a  jmp     loc_1800212AE
0x18002114f  cmp     dword ptr [rdi+4], 0
0x180021153  jz      short loc_18002115F
0x180021155  mov     edx, 1E0h
0x18002115a  jmp     loc_1800212A9
0x18002115f  movsxd  rax, dword ptr [rdi+8]
0x180021163  lea     rcx, dword_1801487F0
0x18002116a  mov     edx, [rbx+13Ch]
0x180021170  mov     ecx, [rcx+rax*4]
0x180021173  mov     [rbx+13Ch], ecx
0x180021179  cmp     ecx, edx
0x18002117b  jz      short loc_180021199
0x18002117d  lea     rcx, [rbx-8]; this
0x180021181  call    ?DefaultAudioDeviceChanged@CVirtualAudioClient@@QEAAJXZ; CVirtualAudioClient::DefaultAudioDeviceChanged(void)
0x180021186  mov     esi, eax
0x180021188  test    eax, eax
0x18002118a  jns     short loc_180021199
0x18002118c  mov     r9d, eax
0x18002118f  mov     edx, 224h
0x180021194  jmp     loc_180021286
0x180021199  mov     rcx, [rbx+88h]
0x1800211a0  mov     rdx, rdi
0x1800211a3  mov     ebp, [rbx+158h]
0x1800211a9  mov     rax, [rcx]
0x1800211ac  mov     rax, [rax+80h]
0x1800211b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800211b8  mov     esi, eax
0x1800211ba  lea     eax, [rsi+7776FFFCh]
0x1800211c0  cmp     eax, 22h ; '"'
0x1800211c3  ja      short loc_180021228
0x1800211c5  mov     rcx, 400000011h
0x1800211cf  bt      rcx, rax
0x1800211d3  jnb     short loc_180021228
0x1800211d5  test    ebp, ebp
0x1800211d7  jz      short loc_180021228
0x1800211d9  cmp     ebp, [rbx+158h]
0x1800211df  jge     short loc_1800211EC
0x1800211e1  mov     ecx, 64h ; 'd'; dwMilliseconds
0x1800211e6  call    cs:__imp_Sleep
0x1800211ec  lea     rcx, [rbx+0D0h]
0x1800211f3  xor     edx, edx
0x1800211f5  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800211fa  lea     rcx, [rbx-8]; this
0x1800211fe  call    ?DefaultAudioDeviceChanged@CVirtualAudioClient@@QEAAJXZ; CVirtualAudioClient::DefaultAudioDeviceChanged(void)
0x180021203  mov     esi, eax
0x180021205  test    eax, eax
0x180021207  js      short loc_180021224
0x180021209  mov     rcx, [rbx+88h]
0x180021210  mov     rdx, rdi
0x180021213  mov     rax, [rcx]
0x180021216  mov     rax, [rax+80h]
0x18002121d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021222  mov     esi, eax
0x180021224  dec     ebp
0x180021226  jmp     short loc_1800211BA
0x180021228  test    esi, esi
0x18002122a  jns     short loc_180021233
0x18002122c  mov     edx, 22Ah
0x180021231  jmp     short loc_180021283
0x180021233  mov     ecx, [rdi]; cb
0x180021235  call    cs:__imp_CoTaskMemAlloc
0x18002123b  mov     rcx, [rbx+130h]; pv
0x180021242  mov     [rbx+130h], rax
0x180021249  test    rcx, rcx
0x18002124c  jz      short loc_180021254
0x18002124e  call    cs:__imp_CoTaskMemFree
0x180021254  mov     rcx, [rbx+130h]; void *
0x18002125b  test    rcx, rcx
0x18002125e  jz      short loc_180021279
0x180021260  mov     r8d, [rdi]; Size
0x180021263  mov     rdx, rdi; Src
0x180021266  call    memcpy_0
0x18002126b  lea     rcx, [rsp+68h+var_48]; this
0x180021270  call    ??1CCritSecLock@ATL@@QEAA@XZ; ATL::CCritSecLock::~CCritSecLock(void)
0x180021275  xor     eax, eax
0x180021277  jmp     short loc_1800212CE
0x180021279  mov     esi, 8007000Eh
0x18002127e  mov     edx, 230h; void *
0x180021283  mov     r9d, esi; char *
0x180021286  mov     rcx, [rsp+68h]; this
0x18002128b  lea     r8, aAvcoreAudiocor_55; "avcore\\audiocore\\client\\audioclient"...
0x180021292  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021297  mov     rcx, r14; lpCriticalSection
0x18002129a  call    cs:__imp_LeaveCriticalSection
0x1800212a0  mov     eax, esi
0x1800212a2  jmp     short loc_1800212CE
0x1800212a4  mov     edx, 1DEh; void *
0x1800212a9  mov     ebx, 80070057h
0x1800212ae  mov     rcx, [rsp+68h]; this
0x1800212b3  lea     r8, aAvcoreAudiocor_55; "avcore\\audiocore\\client\\audioclient"...
0x1800212ba  mov     r9d, ebx; char *
0x1800212bd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800212c2  lea     rcx, [rsp+68h+var_48]; this
0x1800212c7  call    ??1CCritSecLock@ATL@@QEAA@XZ; ATL::CCritSecLock::~CCritSecLock(void)
0x1800212cc  mov     eax, ebx
0x1800212ce  add     rsp, 38h
0x1800212d2  pop     r15
0x1800212d4  pop     r14
0x1800212d6  pop     rdi
0x1800212d7  pop     rsi
0x1800212d8  pop     rbp
0x1800212d9  pop     rbx
0x1800212da  retn
```
