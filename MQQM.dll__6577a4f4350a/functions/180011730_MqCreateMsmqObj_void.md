# MqCreateMsmqObj(void)

- ea: `0x180011730`
- end: `0x1800119db`
- name: `?MqCreateMsmqObj@@YAJXZ`
- size: `683`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180023a00`
- `0x18005e250`

## callees

- `0x18000d1f0`
- `0x18000f35c`
- `0x180011730`
- `0x1800119e4`
- `0x180011f94`
- `0x180012328`
- `0x1800129a8`
- `0x18002c61c`
- `0x1800951bc`
- `0x18009bd1c`
- `0x1800d6ea0`

## import_xrefs

- `msvcrt!free` at `0x1800118fe`
- `msvcrt!free` at `0x1800119af`
- `msvcrt!free` at `0x1800119b9`
- `msvcrt!free` at `0x1800118fe`
- `msvcrt!free` at `0x1800119af`
- `msvcrt!free` at `0x1800119b9`
- `KERNEL32!GetComputerNameExW` at `0x18001179c`
- `KERNEL32!GetComputerNameExW` at `0x1800117d3`
- `KERNEL32!GetComputerNameExW` at `0x18001179c`
- `KERNEL32!GetComputerNameExW` at `0x1800117d3`
- `KERNEL32!GetComputerNameW` at `0x180011815`
- `KERNEL32!GetComputerNameW` at `0x1800118dd`
- `KERNEL32!GetComputerNameW` at `0x180011815`
- `KERNEL32!GetComputerNameW` at `0x1800118dd`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 MqCreateMsmqObj(void)
{
  int v0; // esi
  int v1; // eax
  unsigned int v2; // ebx
  WCHAR *v4; // rbx
  BOOL ComputerName; // ecx
  DWORD v6; // eax
  WCHAR *v7; // rdi
  unsigned int v8; // r14d
  void *v9; // rcx
  int Processing; // esi
  DWORD nSize; // [rsp+30h] [rbp-48h] BYREF
  int v12; // [rsp+34h] [rbp-44h] BYREF
  void *Block; // [rsp+38h] [rbp-40h] BYREF
  WCHAR *v14; // [rsp+40h] [rbp-38h] BYREF
  struct _GUID v15; // [rsp+48h] [rbp-30h] BYREF
  struct _GUID v16; // [rsp+58h] [rbp-20h] BYREF

  v0 = 1;
  v1 = ADInit(0, 1, 0, 1);
  v2 = v1;
  if ( v1 >= 0 )
  {
    nSize = 0;
    v4 = 0;
    v14 = 0;
    ComputerName = GetComputerNameExW(ComputerNameDnsFullyQualified, 0, &nSize);
    v6 = nSize;
    if ( nSize )
    {
      v4 = (WCHAR *)MmAllocate(saturated_mul(nSize, 2u));
      v14 = v4;
      ComputerName = GetComputerNameExW(ComputerNameDnsFullyQualified, v4, &nSize);
      v7 = v4;
      v6 = nSize;
    }
    else
    {
      v7 = 0;
    }
    if ( !ComputerName || !v6 )
    {
      AP<wchar_t>::free(&v14);
      nSize = 17;
      v4 = (WCHAR *)MmAllocate(0x22u);
      v14 = v4;
      GetComputerNameW(v4, &nSize);
      v0 = 0;
      v7 = v4;
    }
    v16 = GUID_NULL;
    v12 = 0;
    Block = 0;
    v15 = GUID_NULL;
    v8 = _CreateTheConfigurationObject(v4, &v16, &Block, &v12, &v15);
    if ( v8 == -1072823025 && v0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_f3280b8dd5f934f498a6d0101b3d1c6c_Traceguids);
      nSize = 17;
      AP<wchar_t>::free(&v14);
      v4 = (WCHAR *)MmAllocate(saturated_mul(nSize, 2u));
      v14 = v4;
      if ( GetComputerNameW(v4, &nSize) && nSize )
      {
        v9 = Block;
        if ( Block )
        {
          Block = 0;
          free(v9);
        }
        v16 = GUID_NULL;
        v8 = _CreateTheConfigurationObject(v4, &v16, &Block, &v12, &v15);
      }
      v7 = v4;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_f3280b8dd5f934f498a6d0101b3d1c6c_Traceguids, v8);
    Processing = PostCreateProcessing(v8, (unsigned int)&v16, (_DWORD)v4, v12, (__int64)&v15);
    if ( Processing < 0 || (Processing = UpdateMachineSecurityReg((__int64)v4, Block, (__int64)&v16), Processing < 0) )
      LogMsgHR(Processing, (wchar_t *)L"qm/creatobj", 0x172u);
    free(Block);
    free(v7);
    return (unsigned int)Processing;
  }
  else
  {
    LogMsgHR(v1, (wchar_t *)L"qm/creatobj", 0x140u);
    return v2;
  }
}

```

## disassembly

```asm
0x180011730  push    rbp
0x180011732  push    rbx
0x180011733  push    rsi
0x180011734  push    rdi
0x180011735  push    r12
0x180011737  push    r14
0x180011739  mov     rbp, rsp
0x18001173c  sub     rsp, 78h
0x180011740  mov     rax, cs:__security_cookie
0x180011747  xor     rax, rsp
0x18001174a  mov     [rbp+var_10], rax
0x18001174e  mov     esi, 1
0x180011753  mov     r9b, sil; bool
0x180011756  xor     r8d, r8d; bool
0x180011759  mov     dl, sil; bool
0x18001175c  xor     ecx, ecx; void (*)(void)
0x18001175e  call    ?ADInit@@YAJP6AXXZ_N11@Z; ADInit(void (*)(void),bool,bool,bool)
0x180011763  mov     ebx, eax
0x180011765  test    eax, eax
0x180011767  jns     short loc_180011784
0x180011769  mov     r8d, 140h; unsigned __int16
0x18001176f  lea     rdx, aQmCreatobj; "qm/creatobj"
0x180011776  mov     ecx, eax; int
0x180011778  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18001177d  mov     eax, ebx
0x18001177f  jmp     loc_1800119C2
0x180011784  mov     [rbp+nSize], 0
0x18001178b  xor     ebx, ebx
0x18001178d  mov     [rbp+var_38], rbx
0x180011791  lea     r8, [rbp+nSize]; nSize
0x180011795  xor     edx, edx; lpBuffer
0x180011797  lea     edi, [rbx+3]
0x18001179a  mov     ecx, edi; NameType
0x18001179c  call    cs:__imp_GetComputerNameExW
0x1800117a2  mov     ecx, eax
0x1800117a4  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800117a8  mov     eax, [rbp+nSize]
0x1800117ab  test    eax, eax
0x1800117ad  jz      short loc_1800117E3
0x1800117af  mov     ecx, eax
0x1800117b1  lea     eax, [rbx+2]
0x1800117b4  mul     rcx
0x1800117b7  cmovb   rax, r8
0x1800117bb  mov     rcx, rax; unsigned __int64
0x1800117be  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x1800117c3  mov     rbx, rax
0x1800117c6  mov     [rbp+var_38], rax
0x1800117ca  lea     r8, [rbp+nSize]; nSize
0x1800117ce  mov     rdx, rax; lpBuffer
0x1800117d1  mov     ecx, edi; NameType
0x1800117d3  call    cs:__imp_GetComputerNameExW
0x1800117d9  mov     ecx, eax
0x1800117db  mov     rdi, rbx
0x1800117de  mov     eax, [rbp+nSize]
0x1800117e1  jmp     short loc_1800117E5
0x1800117e3  xor     edi, edi
0x1800117e5  test    ecx, ecx
0x1800117e7  jz      short loc_1800117ED
0x1800117e9  test    eax, eax
0x1800117eb  jnz     short loc_180011820
0x1800117ed  lea     rcx, [rbp+var_38]
0x1800117f1  call    ?free@?$AP@_W@@QEAAXXZ; AP<wchar_t>::free(void)
0x1800117f6  mov     [rbp+nSize], 11h
0x1800117fd  mov     ecx, 22h ; '"'; unsigned __int64
0x180011802  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x180011807  mov     rbx, rax
0x18001180a  mov     [rbp+var_38], rax
0x18001180e  lea     rdx, [rbp+nSize]; nSize
0x180011812  mov     rcx, rax; lpBuffer
0x180011815  call    cs:__imp_GetComputerNameW
0x18001181b  xor     esi, esi
0x18001181d  mov     rdi, rbx
0x180011820  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180011827  movdqu  xmmword ptr [rbp+var_20.Data1], xmm0
0x18001182c  mov     [rbp+var_44], 0
0x180011833  mov     [rbp+Block], 0
0x18001183b  movdqu  xmmword ptr [rbp+var_30.Data1], xmm0
0x180011840  lea     rax, [rbp+var_30]
0x180011844  mov     [rsp+78h+var_58], rax; struct _GUID *
0x180011849  lea     r9, [rbp+var_44]; int *
0x18001184d  lea     r8, [rbp+Block]; void **
0x180011851  lea     rdx, [rbp+var_20]; struct _GUID *
0x180011855  mov     rcx, rbx; wchar_t *
0x180011858  call    ?_CreateTheConfigurationObject@@YAJPEA_WPEAU_GUID@@PEAPEAXPEAH1@Z; _CreateTheConfigurationObject(wchar_t *,_GUID *,void * *,int *,_GUID *)
0x18001185d  mov     r14d, eax
0x180011860  lea     r12, WPP_GLOBAL_Control
0x180011867  cmp     eax, 0C00E050Fh
0x18001186c  jnz     loc_180011934
0x180011872  test    esi, esi
0x180011874  jz      loc_180011934
0x18001187a  mov     rcx, cs:WPP_GLOBAL_Control
0x180011881  cmp     rcx, r12
0x180011884  jz      short loc_1800118A1
0x180011886  test    byte ptr [rcx+1Ch], 4
0x18001188a  jz      short loc_1800118A1
0x18001188c  mov     edx, 16h
0x180011891  lea     r8, WPP_f3280b8dd5f934f498a6d0101b3d1c6c_Traceguids
0x180011898  mov     rcx, [rcx+10h]
0x18001189c  call    WPP_SF_
0x1800118a1  mov     [rbp+nSize], 11h
0x1800118a8  lea     rcx, [rbp+var_38]
0x1800118ac  call    ?free@?$AP@_W@@QEAAXXZ; AP<wchar_t>::free(void)
0x1800118b1  mov     ecx, [rbp+nSize]
0x1800118b4  mov     eax, 2
0x1800118b9  mul     rcx
0x1800118bc  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800118c3  cmovb   rax, rcx
0x1800118c7  mov     rcx, rax; unsigned __int64
0x1800118ca  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x1800118cf  mov     rbx, rax
0x1800118d2  mov     [rbp+var_38], rax
0x1800118d6  lea     rdx, [rbp+nSize]; nSize
0x1800118da  mov     rcx, rax; lpBuffer
0x1800118dd  call    cs:__imp_GetComputerNameW
0x1800118e3  test    eax, eax
0x1800118e5  jz      short loc_180011931
0x1800118e7  cmp     [rbp+nSize], 0
0x1800118eb  jbe     short loc_180011931
0x1800118ed  mov     rcx, [rbp+Block]; Block
0x1800118f1  test    rcx, rcx
0x1800118f4  jz      short loc_180011905
0x1800118f6  mov     [rbp+Block], 0
0x1800118fe  call    cs:__imp_free
0x180011904  nop
0x180011905  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18001190c  movdqu  xmmword ptr [rbp+var_20.Data1], xmm0
0x180011911  lea     rax, [rbp+var_30]
0x180011915  mov     [rsp+78h+var_58], rax; struct _GUID *
0x18001191a  lea     r9, [rbp+var_44]; int *
0x18001191e  lea     r8, [rbp+Block]; void **
0x180011922  lea     rdx, [rbp+var_20]; struct _GUID *
0x180011926  mov     rcx, rbx; wchar_t *
0x180011929  call    ?_CreateTheConfigurationObject@@YAJPEA_WPEAU_GUID@@PEAPEAXPEAH1@Z; _CreateTheConfigurationObject(wchar_t *,_GUID *,void * *,int *,_GUID *)
0x18001192e  mov     r14d, eax
0x180011931  mov     rdi, rbx
0x180011934  mov     rcx, cs:WPP_GLOBAL_Control
0x18001193b  cmp     rcx, r12
0x18001193e  jz      short loc_18001195E
0x180011940  test    byte ptr [rcx+1Ch], 4
0x180011944  jz      short loc_18001195E
0x180011946  mov     edx, 17h
0x18001194b  mov     r9d, r14d
0x18001194e  lea     r8, WPP_f3280b8dd5f934f498a6d0101b3d1c6c_Traceguids
0x180011955  mov     rcx, [rcx+10h]
0x180011959  call    WPP_SF_d
0x18001195e  lea     rax, [rbp+var_30]
0x180011962  mov     [rsp+78h+var_58], rax
0x180011967  mov     r9d, [rbp+var_44]
0x18001196b  mov     r8, rbx
0x18001196e  lea     rdx, [rbp+var_20]
0x180011972  mov     ecx, r14d
0x180011975  call    _PostCreateProcessing
0x18001197a  mov     esi, eax
0x18001197c  test    eax, eax
0x18001197e  js      short loc_180011996
0x180011980  lea     r8, [rbp+var_20]
0x180011984  mov     rdx, [rbp+Block]
0x180011988  mov     rcx, rbx
0x18001198b  call    _UpdateMachineSecurityReg
0x180011990  mov     esi, eax
0x180011992  test    eax, eax
0x180011994  jns     short loc_1800119AB
0x180011996  mov     r8d, 172h; unsigned __int16
0x18001199c  lea     rdx, aQmCreatobj; "qm/creatobj"
0x1800119a3  mov     ecx, esi; int
0x1800119a5  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x1800119aa  nop
0x1800119ab  mov     rcx, [rbp+Block]; Block
0x1800119af  call    cs:__imp_free
0x1800119b5  nop
0x1800119b6  mov     rcx, rdi; Block
0x1800119b9  call    cs:__imp_free
0x1800119bf  nop
0x1800119c0  mov     eax, esi
0x1800119c2  mov     rcx, [rbp+var_10]
0x1800119c6  xor     rcx, rsp; StackCookie
0x1800119c9  call    __security_check_cookie
0x1800119ce  add     rsp, 78h
0x1800119d2  pop     r14
0x1800119d4  pop     r12
0x1800119d6  pop     rdi
0x1800119d7  pop     rsi
0x1800119d8  pop     rbx
0x1800119d9  pop     rbp
0x1800119da  retn
```
