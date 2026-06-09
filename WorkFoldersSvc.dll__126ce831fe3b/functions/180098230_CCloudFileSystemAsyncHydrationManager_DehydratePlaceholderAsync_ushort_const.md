# CCloudFileSystemAsyncHydrationManager::DehydratePlaceholderAsync(ushort const *)

- ea: `0x180098230`
- end: `0x1800984c0`
- name: `?DehydratePlaceholderAsync@CCloudFileSystemAsyncHydrationManager@@SAJPEBG@Z`
- size: `656`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x1800891b0`
- `0x180092750`

## callees

- `0x180002ab0`
- `0x1800035f8`
- `0x180007e10`
- `0x180007f1c`
- `0x180011314`
- `0x18001137c`
- `0x180021508`
- `0x18003cab8`
- `0x180097f50`
- `0x1800980a4`
- `0x180098230`
- `0x18009879c`

## import_xrefs

- `cldapi!CfDehydratePlaceholder` at `0x1800983b4`
- `cldapi!CfDehydratePlaceholder` at `0x1800983b4`
- `cldapi!CfCloseHandle` at `0x180098486`
- `cldapi!CfCloseHandle` at `0x180098486`
- `cldapi!CfOpenFileWithOplock` at `0x180098350`
- `cldapi!CfOpenFileWithOplock` at `0x180098350`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CCloudFileSystemAsyncHydrationManager::DehydratePlaceholderAsync(const unsigned __int16 *a1)
{
  _DWORD *v2; // rax
  char v3; // cl
  __int16 v4; // ax
  HANDLE *v5; // rsi
  int v6; // eax
  DWORD v7; // ebx
  __int64 v8; // rcx
  unsigned __int64 v9; // rdx
  int v10; // ecx
  unsigned int v11; // ebx
  void *v13; // [rsp+30h] [rbp-D0h] BYREF
  int HydrateHolder; // [rsp+38h] [rbp-C8h] BYREF
  int v15; // [rsp+3Ch] [rbp-C4h]
  char v16; // [rsp+40h] [rbp-C0h]
  const char *v17; // [rsp+48h] [rbp-B8h]
  __int64 v18; // [rsp+50h] [rbp-B0h]
  PVOID pv; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 v20; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v21[2046]; // [rsp+62h] [rbp-9Eh] BYREF

  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) == 0 )
      goto LABEL_8;
    if ( *((_BYTE *)WPP_GLOBAL_Control + 65) >= 6u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 12, WPP_6d192bdd1e183c5353da1b4ba27615c0_Traceguids);
      v2 = WPP_GLOBAL_Control;
    }
  }
  if ( (v2[17] & 0x100) != 0 && *((_BYTE *)v2 + 65) >= 6u )
  {
    v3 = 1;
    goto LABEL_9;
  }
LABEL_8:
  v3 = 0;
LABEL_9:
  v15 = 101;
  v16 = v3;
  v17 = "CCloudFileSystemAsyncHydrationManager::DehydratePlaceholderAsync";
  v18 = 0;
  pv = 0;
  v13 = 0;
  HydrateHolder = 0;
  if ( !a1 )
  {
    HydrateHolder = -2147024809;
    HIWORD(v15) = 108;
    goto LABEL_31;
  }
  HydrateHolder = 0;
  LOWORD(v15) = 108;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 7), 13, WPP_6d192bdd1e183c5353da1b4ba27615c0_Traceguids, a1);
  }
  HydrateHolder = CfOpenFileWithOplock(a1, 5, &v13);
  v4 = 117;
  if ( HydrateHolder >= 0 )
  {
    LOWORD(v15) = 117;
    HydrateHolder = CCloudFileSystemAsyncHydrationManager::CreateHydrateHolder(
                      v13,
                      1,
                      (struct HydrateAsyncHolder **)&pv);
    v4 = 120;
    if ( HydrateHolder >= 0 )
    {
      LOWORD(v15) = 120;
      v5 = (HANDLE *)pv;
      v6 = CfDehydratePlaceholder(v13, 0, -1, 0, pv);
      v7 = v6;
      if ( !v5 )
        goto LABEL_29;
      if ( v6 < 0 )
      {
        if ( v6 == -2147023899 )
        {
          CCloudFileSystemAsyncHydrationManager::SetHydrateCallback(v5);
          goto LABEL_23;
        }
        if ( (Microsoft_Windows_WorkFoldersEnableBits & 0x20) != 0 )
        {
          v20 = 0;
          memset_0(v21, 0, sizeof(v21));
          CEcsFunctionTracer::GetErrorText(v7, v9, &v20);
          McTemplateU0zzd_EventWriteTransfer(
            v10,
            (unsigned int)ECSHOST_EVENT_DEHYDRATION_FAILED,
            (_DWORD)a1,
            (unsigned int)&v20,
            v7);
        }
        HydrateHolder = v7;
        v4 = 145;
      }
      else
      {
        HydrateHolder = CCloudFileSystemAsyncHydrationManager::CloseAndFreeHydrateHolder((struct HydrateAsyncHolder *)v5);
        v4 = 131;
        if ( HydrateHolder >= 0 )
        {
          LOWORD(v15) = 131;
LABEL_23:
          v13 = 0;
          if ( (Microsoft_Windows_WorkFoldersEnableBits & 8) == 0 )
            goto LABEL_31;
          McTemplateU0z_EventWriteTransfer(v8, ECSHOST_EVENT_DEHYDRATION_SUCCESS, a1);
          goto LABEL_29;
        }
      }
    }
  }
  HIWORD(v15) = v4;
LABEL_29:
  if ( v13 )
  {
    CfCloseHandle();
    v13 = 0;
  }
LABEL_31:
  v11 = HydrateHolder;
  CEcsFunctionTracer::~CEcsFunctionTracer((CEcsFunctionTracer *)&HydrateHolder);
  return v11;
}

```

## disassembly

```asm
0x180098230  push    rbp
0x180098232  push    rbx
0x180098233  push    rsi
0x180098234  push    rdi
0x180098235  lea     rbp, [rsp-778h]
0x18009823d  sub     rsp, 878h
0x180098244  mov     rax, cs:__security_cookie
0x18009824b  xor     rax, rsp
0x18009824e  mov     [rbp+790h+var_30], rax
0x180098255  mov     rdi, rcx
0x180098258  lea     rsi, WPP_GLOBAL_Control
0x18009825f  mov     ebx, 100h
0x180098264  mov     rax, cs:WPP_GLOBAL_Control
0x18009826b  cmp     rax, rsi
0x18009826e  jz      short loc_180098297
0x180098270  test    [rax+44h], ebx
0x180098273  jz      short loc_1800982A6
0x180098275  cmp     byte ptr [rax+41h], 6
0x180098279  jb      short loc_180098297
0x18009827b  mov     edx, 0Ch
0x180098280  lea     r8, WPP_6d192bdd1e183c5353da1b4ba27615c0_Traceguids
0x180098287  mov     rcx, [rax+38h]
0x18009828b  call    WPP_SF_
0x180098290  mov     rax, cs:WPP_GLOBAL_Control
0x180098297  test    [rax+44h], ebx
0x18009829a  jz      short loc_1800982A6
0x18009829c  cmp     byte ptr [rax+41h], 6
0x1800982a0  jb      short loc_1800982A6
0x1800982a2  mov     cl, 1
0x1800982a4  jmp     short loc_1800982A8
0x1800982a6  xor     cl, cl
0x1800982a8  mov     [rsp+890h+var_858], 0
0x1800982b0  mov     [rsp+890h+var_854], 65h ; 'e'
0x1800982b8  mov     [rsp+890h+var_850], cl
0x1800982bc  lea     rax, aCcloudfilesyst_47; "CCloudFileSystemAsyncHydrationManager::"...
0x1800982c3  mov     [rsp+890h+var_848], rax
0x1800982c8  mov     [rsp+890h+var_840], 0
0x1800982d1  mov     [rsp+890h+pv], 0
0x1800982da  mov     [rsp+890h+var_860], 0
0x1800982e3  mov     eax, [rsp+890h+var_858]
0x1800982e7  mov     [rsp+890h+var_858], eax
0x1800982eb  mov     eax, 6Ch ; 'l'
0x1800982f0  test    rdi, rdi
0x1800982f3  jnz     short loc_180098307
0x1800982f5  mov     [rsp+890h+var_858], 80070057h
0x1800982fd  mov     word ptr [rsp+890h+var_854+2], ax
0x180098302  jmp     loc_180098495
0x180098307  mov     [rsp+890h+var_858], 0
0x18009830f  mov     word ptr [rsp+890h+var_854], ax
0x180098314  mov     rcx, cs:WPP_GLOBAL_Control
0x18009831b  cmp     rcx, rsi
0x18009831e  jz      short loc_180098343
0x180098320  test    [rcx+44h], ebx
0x180098323  jz      short loc_180098343
0x180098325  cmp     byte ptr [rcx+41h], 4
0x180098329  jb      short loc_180098343
0x18009832b  mov     edx, 0Dh
0x180098330  mov     r9, rdi
0x180098333  lea     r8, WPP_6d192bdd1e183c5353da1b4ba27615c0_Traceguids
0x18009833a  mov     rcx, [rcx+38h]
0x18009833e  call    WPP_SF_S
0x180098343  lea     r8, [rsp+890h+var_860]
0x180098348  mov     edx, 5
0x18009834d  mov     rcx, rdi
0x180098350  call    cs:__imp_CfOpenFileWithOplock
0x180098356  mov     [rsp+890h+var_858], eax
0x18009835a  mov     [rsp+890h+var_858], eax
0x18009835e  test    eax, eax
0x180098360  mov     eax, 75h ; 'u'
0x180098365  js      loc_180098477
0x18009836b  mov     word ptr [rsp+890h+var_854], ax
0x180098370  lea     r8, [rsp+890h+pv]; struct HydrateAsyncHolder **
0x180098375  lea     edx, [rax-74h]; int
0x180098378  mov     rcx, [rsp+890h+var_860]; void *
0x18009837d  call    ?CreateHydrateHolder@CCloudFileSystemAsyncHydrationManager@@CAJPEAXHPEAPEAUHydrateAsyncHolder@@@Z; CCloudFileSystemAsyncHydrationManager::CreateHydrateHolder(void *,int,HydrateAsyncHolder * *)
0x180098382  mov     [rsp+890h+var_858], eax
0x180098386  mov     [rsp+890h+var_858], eax
0x18009838a  test    eax, eax
0x18009838c  mov     eax, 78h ; 'x'
0x180098391  js      loc_180098477
0x180098397  xor     edx, edx
0x180098399  mov     word ptr [rsp+890h+var_854], ax
0x18009839e  mov     rsi, [rsp+890h+pv]
0x1800983a3  mov     [rsp+890h+var_870], rsi
0x1800983a8  xor     r9d, r9d
0x1800983ab  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800983af  mov     rcx, [rsp+890h+var_860]
0x1800983b4  call    cs:__imp_CfDehydratePlaceholder
0x1800983ba  mov     ebx, eax
0x1800983bc  test    rsi, rsi
0x1800983bf  jz      loc_18009847C
0x1800983c5  test    eax, eax
0x1800983c7  js      short loc_1800983ED
0x1800983c9  mov     rcx, rsi; struct HydrateAsyncHolder *
0x1800983cc  call    ?CloseAndFreeHydrateHolder@CCloudFileSystemAsyncHydrationManager@@CAJPEAUHydrateAsyncHolder@@@Z; CCloudFileSystemAsyncHydrationManager::CloseAndFreeHydrateHolder(HydrateAsyncHolder *)
0x1800983d1  mov     [rsp+890h+var_858], eax
0x1800983d5  mov     [rsp+890h+var_858], eax
0x1800983d9  test    eax, eax
0x1800983db  mov     eax, 83h
0x1800983e0  js      loc_180098477
0x1800983e6  mov     word ptr [rsp+890h+var_854], ax
0x1800983eb  jmp     short loc_1800983FD
0x1800983ed  cmp     ebx, 800703E5h
0x1800983f3  jnz     short loc_180098424
0x1800983f5  mov     rcx, rsi; pv
0x1800983f8  call    ?SetHydrateCallback@CCloudFileSystemAsyncHydrationManager@@CAXPEAUHydrateAsyncHolder@@@Z; CCloudFileSystemAsyncHydrationManager::SetHydrateCallback(HydrateAsyncHolder *)
0x1800983fd  mov     [rsp+890h+var_860], 0
0x180098406  test    byte ptr cs:Microsoft_Windows_WorkFoldersEnableBits, 8
0x18009840d  jz      loc_180098495
0x180098413  mov     r8, rdi
0x180098416  lea     rdx, ECSHOST_EVENT_DEHYDRATION_SUCCESS
0x18009841d  call    McTemplateU0z_EventWriteTransfer
0x180098422  jmp     short loc_18009847C
0x180098424  test    byte ptr cs:Microsoft_Windows_WorkFoldersEnableBits, 20h
0x18009842b  jz      short loc_18009846A
0x18009842d  xor     eax, eax
0x18009842f  mov     [rsp+890h+var_830], ax
0x180098434  xor     edx, edx; Val
0x180098436  mov     r8d, 7FEh; Size
0x18009843c  lea     rcx, [rsp+890h+var_82E]; void *
0x180098441  call    memset_0
0x180098446  lea     r8, [rsp+890h+var_830]; unsigned __int16 *
0x18009844b  mov     ecx, ebx; dwMessageId
0x18009844d  call    ?GetErrorText@CEcsFunctionTracer@@SAXJ_KPEAG@Z; CEcsFunctionTracer::GetErrorText(long,unsigned __int64,ushort *)
0x180098452  mov     dword ptr [rsp+890h+var_870], ebx
0x180098456  lea     r9, [rsp+890h+var_830]
0x18009845b  mov     r8, rdi
0x18009845e  lea     rdx, ECSHOST_EVENT_DEHYDRATION_FAILED
0x180098465  call    McTemplateU0zzd_EventWriteTransfer
0x18009846a  mov     [rsp+890h+var_858], ebx
0x18009846e  mov     [rsp+890h+var_858], ebx
0x180098472  mov     eax, 91h
0x180098477  mov     word ptr [rsp+890h+var_854+2], ax
0x18009847c  mov     rcx, [rsp+890h+var_860]
0x180098481  test    rcx, rcx
0x180098484  jz      short loc_180098495
0x180098486  call    cs:__imp_CfCloseHandle
0x18009848c  mov     [rsp+890h+var_860], 0
0x180098495  mov     ebx, [rsp+890h+var_858]
0x180098499  lea     rcx, [rsp+890h+var_858]; this
0x18009849e  call    ??1CEcsFunctionTracer@@QEAA@XZ; CEcsFunctionTracer::~CEcsFunctionTracer(void)
0x1800984a3  mov     eax, ebx
0x1800984a5  mov     rcx, [rbp+790h+var_30]
0x1800984ac  xor     rcx, rsp; StackCookie
0x1800984af  call    __security_check_cookie
0x1800984b4  add     rsp, 878h
0x1800984bb  pop     rdi
0x1800984bc  pop     rsi
0x1800984bd  pop     rbx
0x1800984be  pop     rbp
0x1800984bf  retn
```
