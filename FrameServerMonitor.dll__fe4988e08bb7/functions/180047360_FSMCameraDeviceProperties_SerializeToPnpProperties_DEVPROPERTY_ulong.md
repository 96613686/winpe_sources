# FSMCameraDeviceProperties::SerializeToPnpProperties(_DEVPROPERTY * *,ulong *)

- ea: `0x180047360`
- end: `0x1800474f7`
- name: `?SerializeToPnpProperties@FSMCameraDeviceProperties@@UEAAJPEAPEAU_DEVPROPERTY@@PEAK@Z`
- size: `407`
- prototype: `__int64 __fastcall(FSMCameraDeviceProperties *__hidden this, struct _DEVPROPERTY **, unsigned int *)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800060f8`
- `0x180006a98`
- `0x18001e848`
- `0x180025578`
- `0x180047360`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180047381`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180047381`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800474d7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800474d7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180047408`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180047408`

## pseudocode

```c
__int64 __fastcall FSMCameraDeviceProperties::SerializeToPnpProperties(
        FSMCameraDeviceProperties *this,
        struct _DEVPROPERTY **a2,
        unsigned int *a3)
{
  unsigned int v6; // ebp
  int v7; // edi
  int v8; // r8d
  __int64 v9; // rdx
  __int64 v10; // r15
  __int64 v11; // rdi
  char *v12; // rax
  char *i; // rcx
  struct _DEVPROPERTY *v14; // r13
  __int64 v15; // rdx
  __int64 v16; // rcx
  struct _DEVPROPERTY *v18; // [rsp+70h] [rbp+8h] BYREF
  void *v19; // [rsp+78h] [rbp+10h] BYREF

  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  v6 = 0;
  v18 = 0;
  if ( a2 )
  {
    v10 = *((unsigned int *)this + 16);
    *a2 = 0;
    if ( a3 )
    {
      *a3 = 0;
      v11 = 48 * v10;
      v12 = (char *)CoTaskMemAlloc(48 * v10);
      if ( v12 )
      {
        for ( i = v12; i != &v12[v11]; i += 48 )
        {
          *(_OWORD *)i = 0;
          *((_OWORD *)i + 1) = 0;
          *((_OWORD *)i + 2) = 0;
        }
      }
      v19 = 0;
      wistd::unique_ptr<_DEVPROPERTY [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset<_DEVPROPERTY *>(
        (void **)&v18,
        v12);
      wistd::unique_ptr<_DEVPROPERTY [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(&v19);
      v14 = v18;
      if ( v18 )
      {
        v7 = 0;
        while ( 1 )
        {
          if ( v6 >= (unsigned int)v10 )
          {
            *a2 = v14;
            *a3 = v10;
            v18 = 0;
            goto LABEL_23;
          }
          v16 = *(_QWORD *)(*((_QWORD *)this + 7) + 8LL * v6);
          v7 = (*(__int64 (__fastcall **)(__int64, struct _DEVPROPERTY *))(*(_QWORD *)v16 + 64LL))(v16, &v14[v6]);
          if ( v7 < 0 )
            break;
          ++v6;
        }
        if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          goto LABEL_23;
        v15 = 56;
      }
      else
      {
        v7 = -2147024882;
        if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          goto LABEL_23;
        v15 = 55;
      }
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v15, WPP_dbd64952e28a33ff92c337baa52cb8c3_Traceguids, this, v7);
      goto LABEL_23;
    }
    v7 = -2147467261;
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v9 = 54;
      goto LABEL_4;
    }
  }
  else
  {
    v7 = -2147467261;
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v9 = 53;
LABEL_4:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, WPP_dbd64952e28a33ff92c337baa52cb8c3_Traceguids, this, v8);
    }
  }
LABEL_23:
  wistd::unique_ptr<_DEVPROPERTY [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset((void **)&v18);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180047360  mov     [rsp+arg_10], rbx
0x180047365  push    rbp
0x180047366  push    rsi
0x180047367  push    rdi
0x180047368  push    r12
0x18004736a  push    r13
0x18004736c  push    r14
0x18004736e  push    r15
0x180047370  sub     rsp, 30h
0x180047374  mov     rsi, rcx
0x180047377  mov     r12, r8
0x18004737a  add     rcx, 10h; lpCriticalSection
0x18004737e  mov     r14, rdx
0x180047381  call    cs:__imp_EnterCriticalSection
0x180047387  xor     ebp, ebp
0x180047389  mov     [rsp+68h+arg_0], rbp
0x18004738e  test    r14, r14
0x180047391  jnz     short loc_1800473D0
0x180047393  mov     r8d, 80004003h
0x180047399  mov     edi, r8d
0x18004739c  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800473a1  cmp     al, 1
0x1800473a3  jb      loc_1800474C9
0x1800473a9  lea     edx, [rbp+35h]
0x1800473ac  mov     [rsp+68h+var_48], r8d
0x1800473b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800473b8  lea     r8, WPP_dbd64952e28a33ff92c337baa52cb8c3_Traceguids
0x1800473bf  mov     r9, rsi
0x1800473c2  mov     rcx, [rcx+10h]
0x1800473c6  call    WPP_SF_qD
0x1800473cb  jmp     loc_1800474C9
0x1800473d0  mov     r15d, [rsi+40h]
0x1800473d4  mov     [r14], rbp
0x1800473d7  test    r12, r12
0x1800473da  jnz     short loc_1800473F9
0x1800473dc  mov     r8d, 80004003h
0x1800473e2  mov     edi, r8d
0x1800473e5  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800473ea  cmp     al, 1
0x1800473ec  jb      loc_1800474C9
0x1800473f2  lea     edx, [r12+36h]
0x1800473f7  jmp     short loc_1800473AC
0x1800473f9  lea     rdi, [r15+r15*2]
0x1800473fd  mov     [r12], ebp
0x180047401  shl     rdi, 4
0x180047405  mov     rcx, rdi; cb
0x180047408  call    cs:__imp_CoTaskMemAlloc
0x18004740e  test    rax, rax
0x180047411  jz      short loc_180047436
0x180047413  lea     rdx, [rdi+rax]
0x180047417  mov     rcx, rax
0x18004741a  cmp     rax, rdx
0x18004741d  jz      short loc_180047436
0x18004741f  xorps   xmm0, xmm0
0x180047422  movups  xmmword ptr [rcx], xmm0
0x180047425  movups  xmmword ptr [rcx+10h], xmm0
0x180047429  movups  xmmword ptr [rcx+20h], xmm0
0x18004742d  add     rcx, 30h ; '0'
0x180047431  cmp     rcx, rdx
0x180047434  jnz     short loc_18004741F
0x180047436  mov     rdx, rax
0x180047439  mov     [rsp+68h+arg_8], rbp
0x18004743e  lea     rcx, [rsp+68h+arg_0]
0x180047443  call    ??$reset@PEAU_DEVPROPERTY@@@?$unique_ptr@$$BY0A@U_DEVPROPERTY@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAXPEAU_DEVPROPERTY@@@Z; wistd::unique_ptr<_DEVPROPERTY [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::reset<_DEVPROPERTY *>(_DEVPROPERTY *)
0x180047448  lea     rcx, [rsp+68h+arg_8]
0x18004744d  call    ?reset@?$unique_ptr@$$BY0A@U_DEVPROPERTY@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<_DEVPROPERTY [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::reset(std::nullptr_t)
0x180047452  mov     r13, [rsp+68h+arg_0]
0x180047457  test    r13, r13
0x18004745a  jnz     short loc_180047477
0x18004745c  mov     edi, 8007000Eh
0x180047461  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180047466  cmp     al, 1
0x180047468  jb      short loc_1800474C9
0x18004746a  lea     edx, [r13+37h]
0x18004746e  mov     [rsp+68h+var_48], edi
0x180047472  jmp     loc_1800473B1
0x180047477  mov     edi, ebp
0x180047479  cmp     ebp, r15d
0x18004747c  jnb     short loc_1800474B9
0x18004747e  mov     rax, [rsi+38h]
0x180047482  mov     edx, ebp
0x180047484  mov     rcx, [rax+rdx*8]
0x180047488  lea     rdx, [rdx+rdx*2]
0x18004748c  shl     rdx, 4
0x180047490  add     rdx, r13
0x180047493  mov     rax, [rcx]
0x180047496  mov     rax, [rax+40h]
0x18004749a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004749f  mov     edi, eax
0x1800474a1  test    eax, eax
0x1800474a3  js      short loc_1800474A9
0x1800474a5  inc     ebp
0x1800474a7  jmp     short loc_180047479
0x1800474a9  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800474ae  cmp     al, 1
0x1800474b0  jb      short loc_1800474C9
0x1800474b2  mov     edx, 38h ; '8'
0x1800474b7  jmp     short loc_18004746E
0x1800474b9  mov     [r14], r13
0x1800474bc  mov     [r12], r15d
0x1800474c0  mov     [rsp+68h+arg_0], 0
0x1800474c9  lea     rcx, [rsp+68h+arg_0]
0x1800474ce  call    ?reset@?$unique_ptr@$$BY0A@U_DEVPROPERTY@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<_DEVPROPERTY [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::reset(std::nullptr_t)
0x1800474d3  lea     rcx, [rsi+10h]; lpCriticalSection
0x1800474d7  call    cs:__imp_LeaveCriticalSection
0x1800474dd  mov     rbx, [rsp+68h+arg_10]
0x1800474e5  mov     eax, edi
0x1800474e7  add     rsp, 30h
0x1800474eb  pop     r15
0x1800474ed  pop     r14
0x1800474ef  pop     r13
0x1800474f1  pop     r12
0x1800474f3  pop     rdi
0x1800474f4  pop     rsi
0x1800474f5  pop     rbp
0x1800474f6  retn
```
