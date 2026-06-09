# MBAE_INTERFACE_CONTEXT::CreateBindingDeviceNode(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,_GUID const *,bool,int,_DEVPROPERTY *,void (*)(HSWDEVICE__ *,long,void *,ushort const *),int)

- ea: `0x1800b8a2c`
- end: `0x1800b8d08`
- name: `?CreateBindingDeviceNode@MBAE_INTERFACE_CONTEXT@@QEAAJPEBG000000PEBU_GUID@@_NHPEAU_DEVPROPERTY@@P6AXPEAUHSWDEVICE__@@JPEAX0@ZH@Z`
- size: `732`
- prototype: `int(MBAE_INTERFACE_CONTEXT *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const struct _GUID *, bool, int, struct _DEVPROPERTY *, void (*)(struct HSWDEVICE__ *, int, void *, const unsigned __int16 *), int)`
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800b9164`

## callees

- `0x1800094f4`
- `0x18000f0f4`
- `0x180012300`
- `0x180016c50`
- `0x180019f24`
- `0x180074758`
- `0x1800b8a2c`
- `0x1800b90b4`
- `0x1800b937c`
- `0x1800c5d28`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800b8b4c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800b8b4c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b8ca8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b8ca8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b8a99`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b8cae`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b8a99`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b8cae`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800b8aaa`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800b8aaa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800b8cbc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800b8cbc`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceCreate` at `0x1800b8c39`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceCreate` at `0x1800b8c39`

## string_xrefs

- `0x1800b8b67`: `MBAEUpdaterStopping`
- `0x1800b8a5b`: `MBAE_INTERFACE_CONTEXT::CreateBindingDeviceNode`
- `0x1800b8c51`: `MBAE_INTERFACE_CONTEXT::CreateBindingDeviceNode`
- `0x1800b8cdf`: `MBAE_INTERFACE_CONTEXT::CreateBindingDeviceNode`
- `0x1800b8c48`: `SwDeviceCreate failed, hr = 0x%8x`

## pseudocode

```c
__int64 __fastcall MBAE_INTERFACE_CONTEXT::CreateBindingDeviceNode(
        MBAE_INTERFACE_CONTEXT *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *a5,
        const unsigned __int16 *a6,
        const unsigned __int16 *a7,
        const unsigned __int16 *a8,
        const struct _GUID *a9,
        bool a10,
        int a11,
        struct _DEVPROPERTY *a12,
        void (*a13)(struct HSWDEVICE__ *, int, void *, const unsigned __int16 *),
        unsigned int a14)
{
  int v17; // ebx
  HANDLE ProcessHeap; // rax
  char *v19; // rdi
  int CallbackContext; // ebx
  unsigned int v21; // edx
  __int64 v22; // rax
  __int64 v23; // rcx
  __int128 v24; // xmm1
  __int128 v25; // xmm0
  __int64 i; // r8
  __int64 v27; // rdx
  __int64 v28; // rcx
  int v29; // ecx
  int v30; // eax
  unsigned __int16 *v31; // rcx
  const unsigned __int16 *v32; // r8
  HANDLE v33; // rax
  unsigned int v34; // edx
  __int64 v36; // [rsp+48h] [rbp-59h] BYREF
  LPVOID lpMem; // [rsp+50h] [rbp-51h]
  __int64 v38; // [rsp+58h] [rbp-49h] BYREF
  _QWORD v39[4]; // [rsp+60h] [rbp-41h] BYREF
  int v40; // [rsp+80h] [rbp-21h]
  const unsigned __int16 *v41; // [rsp+88h] [rbp-19h]
  unsigned int v44; // [rsp+138h] [rbp+97h]

  v36 = 0;
  v17 = a11 + 4;
  v44 = a11 + 4;
  WwanLog::Enter("MBAE_INTERFACE_CONTEXT::CreateBindingDeviceNode");
  if ( a14 > 2 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  ProcessHeap = GetProcessHeap();
  v19 = (char *)HeapAlloc(ProcessHeap, 8u, 48LL * v17);
  if ( !v19 )
  {
    CallbackContext = -2147024882;
LABEL_24:
    v34 = (unsigned __int16)CallbackContext;
    goto LABEL_26;
  }
  CallbackContext = 0;
  v21 = 0;
  do
  {
    v22 = (int)v21++;
    v23 = 6 * v22;
    v24 = *(_OWORD *)&qword_180151F50[6 * v22 + 2];
    *(_OWORD *)&v19[8 * v23] = *(_OWORD *)&qword_180151F50[v23];
    v25 = *(_OWORD *)&qword_180151F50[6 * v22 + 4];
    *(_OWORD *)&v19[8 * v23 + 16] = v24;
    *(_OWORD *)&v19[8 * v23 + 32] = v25;
  }
  while ( v21 < 4 );
  for ( i = 0; (int)i < a11; *(_OWORD *)&v19[8 * v28 + 32] = *(_OWORD *)&a12[v27].Type )
  {
    v27 = i;
    v28 = 3 * (i + 4);
    i = (unsigned int)(i + 1);
    v28 *= 2;
    *(DEVPROPGUID *)&v19[8 * v28] = a12[v27].CompKey.Key.fmtid;
    *(_OWORD *)&v19[8 * v28 + 16] = *(_OWORD *)&a12[v27].CompKey.Key.pid;
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 528));
  v36 = *((_QWORD *)this + (int)a14 + 91);
  WwanLog::Verbose("MBAEUpdaterStopping", 0, &String1);
  if ( !byte_180152B84 && !v36 )
  {
    lpMem = 0;
    CallbackContext = AllocSwDeviceCreateCallbackContext(a2, a3);
    if ( CallbackContext >= 0 )
    {
      v38 = 72;
      memset_0(v39, 0, 0x40u);
      v29 = 6;
      v39[0] = a4;
      v39[1] = a7;
      v39[2] = a8;
      v41 = a6;
      v39[3] = a9;
      if ( a10 )
        v29 = 7;
      v40 = v29;
      v30 = ((__int64 (__fastcall *)(const wchar_t *, const unsigned __int16 *, __int64 *, _QWORD, char *, void (*)(struct HSWDEVICE__ *, int, void *, const unsigned __int16 *), LPVOID, __int64 *))SwDeviceCreate)(
              L"MBAE",
              a5,
              &v38,
              v44,
              v19,
              a13,
              lpMem,
              &v36);
      CallbackContext = v30;
      if ( v30 < 0 )
      {
        WwanLog::Error(
          "MBAE_INTERFACE_CONTEXT::CreateBindingDeviceNode",
          0,
          L"SwDeviceCreate failed, hr = 0x%8x",
          (unsigned int)v30);
        FreeSwDeviceCreateCallbackContext(lpMem);
        goto LABEL_21;
      }
      *((_QWORD *)this + (int)a14 + 91) = v36;
      if ( a14 )
      {
        if ( a14 - 1 > 1 )
          goto LABEL_21;
        v32 = a2;
        v31 = (unsigned __int16 *)((char *)this + 648);
      }
      else
      {
        v31 = (unsigned __int16 *)((char *)this + 568);
        v32 = a3;
      }
      CallbackContext = StringCchCopyW(v31, 0x28u, v32);
    }
  }
LABEL_21:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 528));
  v33 = GetProcessHeap();
  HeapFree(v33, 0, v19);
  if ( CallbackContext < 0 )
  {
    if ( (CallbackContext & 0x1FFF0000) != 0x70000 )
    {
      v34 = CallbackContext;
      goto LABEL_26;
    }
    goto LABEL_24;
  }
  v34 = 0;
LABEL_26:
  WwanLog::ExitWithStatus("MBAE_INTERFACE_CONTEXT::CreateBindingDeviceNode", v34);
  return (unsigned int)CallbackContext;
}

```

## disassembly

```asm
0x1800b8a2c  mov     rax, rsp
0x1800b8a2f  mov     [rax+8], rbx
0x1800b8a33  mov     [rax+20h], r9
0x1800b8a37  mov     [rax+10h], rdx
0x1800b8a3b  push    rbp
0x1800b8a3c  push    rsi
0x1800b8a3d  push    rdi
0x1800b8a3e  push    r12
0x1800b8a40  push    r13
0x1800b8a42  push    r14
0x1800b8a44  push    r15
0x1800b8a46  lea     rbp, [rax-3Fh]
0x1800b8a4a  sub     rsp, 0A0h
0x1800b8a51  mov     r15d, [rbp+37h+arg_50]
0x1800b8a58  mov     rsi, rcx
0x1800b8a5b  lea     rcx, aMbaeInterfaceC; "MBAE_INTERFACE_CONTEXT::CreateBindingDe"...
0x1800b8a62  mov     [rbp+37h+var_90], 0
0x1800b8a6a  mov     r13, r8
0x1800b8a6d  lea     ebx, [r15+4]
0x1800b8a71  mov     [rbp+37h+arg_50], ebx
0x1800b8a77  call    ?Enter@WwanLog@@SAXPEBD@Z; WwanLog::Enter(char const *)
0x1800b8a7c  movsxd  r14, [rbp+37h+arg_68]
0x1800b8a83  cmp     r14d, 2
0x1800b8a87  jbe     short loc_1800B8A8E
0x1800b8a89  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800b8a8e  movsxd  rax, ebx
0x1800b8a91  lea     rbx, [rax+rax*2]
0x1800b8a95  shl     rbx, 4
0x1800b8a99  call    cs:__imp_GetProcessHeap
0x1800b8a9f  mov     r8, rbx; dwBytes
0x1800b8aa2  mov     edx, 8; dwFlags
0x1800b8aa7  mov     rcx, rax; hHeap
0x1800b8aaa  call    cs:__imp_HeapAlloc
0x1800b8ab0  mov     rdi, rax
0x1800b8ab3  test    rax, rax
0x1800b8ab6  jnz     short loc_1800B8AC2
0x1800b8ab8  mov     ebx, 8007000Eh
0x1800b8abd  jmp     loc_1800B8CD8
0x1800b8ac2  xor     ebx, ebx
0x1800b8ac4  xor     edx, edx
0x1800b8ac6  movsxd  rax, edx
0x1800b8ac9  inc     edx
0x1800b8acb  lea     rcx, [rax+rax*2]
0x1800b8acf  add     rcx, rcx
0x1800b8ad2  lea     rax, qword_180151F50
0x1800b8ad9  movups  xmm0, xmmword ptr [rax+rcx*8]
0x1800b8add  movups  xmm1, xmmword ptr [rax+rcx*8+10h]
0x1800b8ae2  movups  xmmword ptr [rdi+rcx*8], xmm0
0x1800b8ae6  movups  xmm0, xmmword ptr [rax+rcx*8+20h]
0x1800b8aeb  movups  xmmword ptr [rdi+rcx*8+10h], xmm1
0x1800b8af0  movups  xmmword ptr [rdi+rcx*8+20h], xmm0
0x1800b8af5  cmp     edx, 4
0x1800b8af8  jb      short loc_1800B8AC6
0x1800b8afa  xor     r8d, r8d
0x1800b8afd  test    r15d, r15d
0x1800b8b00  jle     short loc_1800B8B42
0x1800b8b02  mov     r9, [rbp+37h+arg_58]
0x1800b8b09  lea     rdx, [r8+r8*2]
0x1800b8b0d  add     rdx, rdx
0x1800b8b10  lea     rcx, [r8+4]
0x1800b8b14  lea     rcx, [rcx+rcx*2]
0x1800b8b18  inc     r8d
0x1800b8b1b  add     rcx, rcx
0x1800b8b1e  movups  xmm0, xmmword ptr [r9+rdx*8]
0x1800b8b23  movups  xmmword ptr [rdi+rcx*8], xmm0
0x1800b8b27  movups  xmm1, xmmword ptr [r9+rdx*8+10h]
0x1800b8b2d  movups  xmmword ptr [rdi+rcx*8+10h], xmm1
0x1800b8b32  movups  xmm0, xmmword ptr [r9+rdx*8+20h]
0x1800b8b38  movups  xmmword ptr [rdi+rcx*8+20h], xmm0
0x1800b8b3d  cmp     r8d, r15d
0x1800b8b40  jl      short loc_1800B8B09
0x1800b8b42  lea     r12, [rsi+210h]
0x1800b8b49  mov     rcx, r12; lpCriticalSection
0x1800b8b4c  call    cs:__imp_EnterCriticalSection
0x1800b8b52  mov     rax, [rsi+r14*8+2D8h]
0x1800b8b5a  lea     r8, String1; unsigned __int16 *
0x1800b8b61  xor     edx, edx; struct _GUID *
0x1800b8b63  mov     [rbp+37h+var_90], rax
0x1800b8b67  lea     rcx, aMbaeupdatersto_0; "MBAEUpdaterStopping"
0x1800b8b6e  call    ?Verbose@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Verbose(char const *,_GUID const *,ushort const *,...)
0x1800b8b73  mov     al, cs:byte_180152B84
0x1800b8b79  test    al, al
0x1800b8b7b  jnz     loc_1800B8CA5
0x1800b8b81  cmp     [rbp+37h+var_90], rbx
0x1800b8b85  jnz     loc_1800B8CA5
0x1800b8b8b  mov     rcx, [rbp+37h+arg_8]; unsigned __int16 *
0x1800b8b8f  lea     r8, [rbp+37h+lpMem]
0x1800b8b93  mov     rdx, r13; unsigned __int16 *
0x1800b8b96  mov     [rbp+37h+lpMem], rbx
0x1800b8b9a  call    _AllocSwDeviceCreateCallbackContext
0x1800b8b9f  mov     ebx, eax
0x1800b8ba1  test    eax, eax
0x1800b8ba3  js      loc_1800B8CA5
0x1800b8ba9  xor     edx, edx; Val
0x1800b8bab  mov     [rbp+37h+var_80], 48h ; 'H'
0x1800b8bb3  lea     rcx, [rbp+37h+var_78]; void *
0x1800b8bb7  lea     r8d, [rdx+40h]; Size
0x1800b8bbb  call    memset_0
0x1800b8bc0  mov     rax, [rbp+37h+arg_18]
0x1800b8bc4  lea     r8, [rbp+37h+var_80]
0x1800b8bc8  cmp     [rbp+37h+arg_48], 0
0x1800b8bcf  mov     ecx, 6
0x1800b8bd4  mov     r9d, [rbp+37h+arg_50]
0x1800b8bdb  mov     rdx, [rbp+37h+arg_20]
0x1800b8bdf  mov     [rbp+37h+var_78], rax
0x1800b8be3  mov     rax, [rbp+37h+arg_30]
0x1800b8be7  mov     [rbp+37h+var_70], rax
0x1800b8beb  mov     rax, [rbp+37h+arg_38]
0x1800b8bef  mov     [rbp+37h+var_68], rax
0x1800b8bf3  mov     rax, [rbp+37h+arg_28]
0x1800b8bf7  mov     [rbp+37h+var_50], rax
0x1800b8bfb  mov     rax, [rbp+37h+arg_40]
0x1800b8c02  mov     [rbp+37h+var_60], rax
0x1800b8c06  lea     eax, [rcx+1]
0x1800b8c09  cmovnz  ecx, eax
0x1800b8c0c  lea     rax, [rbp+37h+var_90]
0x1800b8c10  mov     [rsp+38h], rax
0x1800b8c15  mov     rax, [rbp+37h+lpMem]
0x1800b8c19  mov     [rsp+0D0h+var_A0], rax
0x1800b8c1e  mov     rax, [rbp+37h+arg_60]
0x1800b8c25  mov     [rbp+37h+var_58], ecx
0x1800b8c28  lea     rcx, aMbae; "MBAE"
0x1800b8c2f  mov     [rsp+0D0h+var_A8], rax
0x1800b8c34  mov     [rsp+0D0h+var_B0], rdi
0x1800b8c39  call    cs:__imp_SwDeviceCreate
0x1800b8c3f  mov     ebx, eax
0x1800b8c41  test    eax, eax
0x1800b8c43  jns     short loc_1800B8C68
0x1800b8c45  mov     r9d, eax
0x1800b8c48  lea     r8, aSwdevicecreate_1; "SwDeviceCreate failed, hr = 0x%8x"
0x1800b8c4f  xor     edx, edx; struct _GUID *
0x1800b8c51  lea     rcx, aMbaeInterfaceC; "MBAE_INTERFACE_CONTEXT::CreateBindingDe"...
0x1800b8c58  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800b8c5d  mov     rcx, [rbp+37h+lpMem]; lpMem
0x1800b8c61  call    _FreeSwDeviceCreateCallbackContext
0x1800b8c66  jmp     short loc_1800B8CA5
0x1800b8c68  mov     rax, [rbp+37h+var_90]
0x1800b8c6c  mov     [rsi+r14*8+2D8h], rax
0x1800b8c74  test    r14d, r14d
0x1800b8c77  jnz     short loc_1800B8C85
0x1800b8c79  lea     rcx, [rsi+238h]
0x1800b8c80  mov     r8, r13
0x1800b8c83  jmp     short loc_1800B8C99
0x1800b8c85  lea     eax, [r14-1]
0x1800b8c89  cmp     eax, 1
0x1800b8c8c  ja      short loc_1800B8CA5
0x1800b8c8e  mov     r8, [rbp+37h+arg_8]; unsigned __int16 *
0x1800b8c92  lea     rcx, [rsi+288h]; unsigned __int16 *
0x1800b8c99  mov     edx, 28h ; '('; unsigned __int64
0x1800b8c9e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800b8ca3  mov     ebx, eax
0x1800b8ca5  mov     rcx, r12; lpCriticalSection
0x1800b8ca8  call    cs:__imp_LeaveCriticalSection
0x1800b8cae  call    cs:__imp_GetProcessHeap
0x1800b8cb4  mov     r8, rdi; lpMem
0x1800b8cb7  xor     edx, edx; dwFlags
0x1800b8cb9  mov     rcx, rax; hHeap
0x1800b8cbc  call    cs:__imp_HeapFree
0x1800b8cc2  test    ebx, ebx
0x1800b8cc4  js      short loc_1800B8CCA
0x1800b8cc6  xor     edx, edx
0x1800b8cc8  jmp     short loc_1800B8CDF
0x1800b8cca  mov     eax, ebx
0x1800b8ccc  and     eax, 1FFF0000h
0x1800b8cd1  cmp     eax, 70000h
0x1800b8cd6  jnz     short loc_1800B8CDD
0x1800b8cd8  movzx   edx, bx
0x1800b8cdb  jmp     short loc_1800B8CDF
0x1800b8cdd  mov     edx, ebx; unsigned int
0x1800b8cdf  lea     rcx, aMbaeInterfaceC; "MBAE_INTERFACE_CONTEXT::CreateBindingDe"...
0x1800b8ce6  call    ?ExitWithStatus@WwanLog@@SAXPEBDK@Z; WwanLog::ExitWithStatus(char const *,ulong)
0x1800b8ceb  mov     eax, ebx
0x1800b8ced  mov     rbx, [rsp+0D0h+arg_0]
0x1800b8cf5  add     rsp, 0A0h
0x1800b8cfc  pop     r15
0x1800b8cfe  pop     r14
0x1800b8d00  pop     r13
0x1800b8d02  pop     r12
0x1800b8d04  pop     rdi
0x1800b8d05  pop     rsi
0x1800b8d06  pop     rbp
0x1800b8d07  retn
```
