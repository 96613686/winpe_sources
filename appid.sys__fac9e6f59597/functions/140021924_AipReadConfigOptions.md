# AipReadConfigOptions

- ea: `0x140021924`
- end: `0x140021b48`
- name: `AipReadConfigOptions`
- size: `548`
- prototype: `__int64()`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x140033f50`
- `0x1400380c4`

## callees

- `0x140006a20`
- `0x140021924`
- `0x14002522c`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x140021afd`
- `ntoskrnl!ExReleaseResourceLite` at `0x140021afd`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140021a9e`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140021a9e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140021b09`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140021b09`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140021a89`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140021a89`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x140021a75`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x140021a75`

## string_xrefs

- `0x140021978`: `EnablePath`
- `0x140021a21`: `\Registry\Machine\System\CurrentControlSet\Control\AppID\`

## pseudocode

```c
__int64 AipReadConfigOptions()
{
  __int64 result; // rax
  __int128 v1; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v2[2]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v3; // [rsp+50h] [rbp-B0h] BYREF
  int v4; // [rsp+58h] [rbp-A8h]
  const wchar_t *v5; // [rsp+60h] [rbp-A0h]
  __int128 *v6; // [rsp+68h] [rbp-98h]
  int v7; // [rsp+70h] [rbp-90h]
  char *v8; // [rsp+78h] [rbp-88h]
  int v9; // [rsp+80h] [rbp-80h]
  __int64 v10; // [rsp+88h] [rbp-78h]
  int v11; // [rsp+90h] [rbp-70h]
  const wchar_t *v12; // [rsp+98h] [rbp-68h]
  char *v13; // [rsp+A0h] [rbp-60h]
  int v14; // [rsp+A8h] [rbp-58h]
  char *v15; // [rsp+B0h] [rbp-50h]
  int v16; // [rsp+B8h] [rbp-48h]
  __int64 v17; // [rsp+C0h] [rbp-40h]
  int v18; // [rsp+C8h] [rbp-38h]
  const wchar_t *v19; // [rsp+D0h] [rbp-30h]
  char *v20; // [rsp+D8h] [rbp-28h]
  int v21; // [rsp+E0h] [rbp-20h]
  char *v22; // [rsp+E8h] [rbp-18h]
  int v23; // [rsp+F0h] [rbp-10h]
  __int64 v24; // [rsp+F8h] [rbp-8h]
  int v25; // [rsp+100h] [rbp+0h]
  const wchar_t *v26; // [rsp+108h] [rbp+8h]
  _QWORD *v27; // [rsp+110h] [rbp+10h]
  int v28; // [rsp+118h] [rbp+18h]
  char *v29; // [rsp+120h] [rbp+20h]
  int v30; // [rsp+128h] [rbp+28h]
  __int64 v31; // [rsp+130h] [rbp+30h]
  int v32; // [rsp+138h] [rbp+38h]
  const wchar_t *v33; // [rsp+140h] [rbp+40h]
  char *v34; // [rsp+148h] [rbp+48h]
  int v35; // [rsp+150h] [rbp+50h]
  char *v36; // [rsp+158h] [rbp+58h]
  int v37; // [rsp+160h] [rbp+60h]
  __int64 v38; // [rsp+168h] [rbp+68h]
  int v39; // [rsp+170h] [rbp+70h]
  __int64 v40; // [rsp+178h] [rbp+78h]
  __int64 v41; // [rsp+180h] [rbp+80h]
  int v42; // [rsp+188h] [rbp+88h]
  __int64 v43; // [rsp+190h] [rbp+90h]
  int v44; // [rsp+198h] [rbp+98h]

  v8 = byte_140019190;
  v2[0] = 0;
  v4 = 288;
  v7 = 67108868;
  v9 = 4;
  v5 = L"EnablePath";
  v11 = 288;
  v6 = &v1;
  v12 = L"EnableFqbn";
  v13 = (char *)&v1 + 4;
  v19 = L"EnableSha256FlatHash";
  v20 = (char *)&v1 + 12;
  v26 = L"EnableSha1Hash";
  v27 = v2;
  v33 = L"EnableSha256Hash";
  v14 = 67108868;
  v15 = byte_140019190;
  v16 = 4;
  v18 = 288;
  v21 = 67108868;
  v22 = byte_140019190;
  v23 = 4;
  v25 = 288;
  v28 = 67108868;
  v29 = byte_140019190;
  v30 = 4;
  v32 = 288;
  v35 = 67108868;
  v36 = byte_140019190;
  v37 = 4;
  v34 = (char *)v2 + 4;
  v1 = 0;
  v3 = 0;
  v10 = 0;
  v17 = 0;
  v24 = 0;
  v31 = 0;
  v38 = 0;
  v39 = 0;
  v40 = 0;
  v41 = 0;
  v42 = 0;
  v43 = 0;
  v44 = 0;
  result = RtlQueryRegistryValuesEx(0, L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\AppID\\", &v3, 0, 0);
  if ( (int)result >= 0 )
  {
    KeEnterCriticalRegion();
    ExAcquireResourceExclusiveLite((PERESOURCE)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels, 1u);
    *(_OWORD *)&WPP_MAIN_CB.Dpc.TargetInfoAsUlong = v1;
    WPP_MAIN_CB.Dpc.ProcessorHistory = v2[0];
    ExReleaseResourceLite((PERESOURCE)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels);
    KeLeaveCriticalRegion();
    if ( (unsigned int)(DWORD1(v1) - 1) <= 0xFFFFFFFD )
      AiLogTriggerServiceStartEvent();
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x140021924  mov     [rsp-8+arg_0], rbx
0x140021929  push    rbp
0x14002192a  lea     rbp, [rsp-0B0h]
0x140021932  sub     rsp, 1B0h
0x140021939  mov     rax, cs:__security_cookie
0x140021940  xor     rax, rsp
0x140021943  mov     [rbp+0B0h+var_10], rax
0x14002194a  xor     ebx, ebx
0x14002194c  lea     rdx, byte_140019190
0x140021953  xor     eax, eax
0x140021955  mov     [rsp+1B0h+var_138], rdx
0x14002195a  mov     [rsp+1B0h+var_170], rax
0x14002195f  mov     r9d, 120h
0x140021965  mov     r8d, 4000004h
0x14002196b  mov     [rsp+1B0h+var_158], r9d
0x140021970  lea     ecx, [rbx+4]
0x140021973  mov     [rsp+1B0h+var_140], r8d
0x140021978  lea     rax, aEnablepath; "EnablePath"
0x14002197f  mov     [rbp+0B0h+var_130], ecx
0x140021982  mov     [rsp+1B0h+var_150], rax
0x140021987  xorps   xmm0, xmm0
0x14002198a  lea     rax, [rsp+1B0h+var_180]
0x14002198f  mov     [rbp+0B0h+var_120], r9d
0x140021993  mov     [rsp+1B0h+var_148], rax
0x140021998  lea     rax, aEnablefqbn; "EnableFqbn"
0x14002199f  mov     [rbp+0B0h+var_118], rax
0x1400219a3  lea     rax, [rsp+1B0h+var_180+4]
0x1400219a8  mov     [rbp+0B0h+var_110], rax
0x1400219ac  lea     rax, aEnablesha256fl; "EnableSha256FlatHash"
0x1400219b3  mov     [rbp+0B0h+var_E0], rax
0x1400219b7  lea     rax, [rsp+1B0h+var_180+0Ch]
0x1400219bc  mov     [rbp+0B0h+var_D8], rax
0x1400219c0  lea     rax, aEnablesha1hash; "EnableSha1Hash"
0x1400219c7  mov     [rbp+0B0h+var_A8], rax
0x1400219cb  lea     rax, [rsp+1B0h+var_170]
0x1400219d0  mov     [rbp+0B0h+var_A0], rax
0x1400219d4  lea     rax, aEnablesha256ha; "EnableSha256Hash"
0x1400219db  mov     [rbp+0B0h+var_70], rax
0x1400219df  lea     rax, [rsp+1B0h+var_170+4]
0x1400219e4  mov     [rbp+0B0h+var_108], r8d
0x1400219e8  mov     [rbp+0B0h+var_100], rdx
0x1400219ec  mov     [rbp+0B0h+var_F8], ecx
0x1400219ef  mov     [rbp+0B0h+var_E8], r9d
0x1400219f3  mov     [rbp+0B0h+var_D0], r8d
0x1400219f7  mov     [rbp+0B0h+var_C8], rdx
0x1400219fb  mov     [rbp+0B0h+var_C0], ecx
0x1400219fe  mov     [rbp+0B0h+var_B0], r9d
0x140021a02  mov     [rbp+0B0h+var_98], r8d
0x140021a06  mov     [rbp+0B0h+var_90], rdx
0x140021a0a  mov     [rbp+0B0h+var_88], ecx
0x140021a0d  mov     [rbp+0B0h+var_78], r9d
0x140021a11  xor     r9d, r9d
0x140021a14  mov     [rbp+0B0h+var_60], r8d
0x140021a18  lea     r8, [rsp+1B0h+var_160]
0x140021a1d  mov     [rbp+0B0h+var_58], rdx
0x140021a21  lea     rdx, aRegistryMachin_8; "\\Registry\\Machine\\System\\CurrentCon"...
0x140021a28  mov     [rbp+0B0h+var_50], ecx
0x140021a2b  xor     ecx, ecx
0x140021a2d  mov     [rbp+0B0h+var_68], rax
0x140021a31  movups  [rsp+1B0h+var_180], xmm0
0x140021a36  mov     [rsp+1B0h+var_160], rbx
0x140021a3b  mov     [rbp+0B0h+var_128], rbx
0x140021a3f  mov     [rbp+0B0h+var_F0], rbx
0x140021a43  mov     [rbp+0B0h+var_B8], rbx
0x140021a47  mov     [rbp+0B0h+var_80], rbx
0x140021a4b  mov     [rbp+0B0h+var_48], rbx
0x140021a4f  mov     [rbp+0B0h+var_40], ebx
0x140021a52  mov     [rbp+0B0h+var_38], rbx
0x140021a56  mov     [rbp+0B0h+var_30], rbx
0x140021a5d  mov     [rbp+0B0h+var_28], ebx
0x140021a63  mov     [rbp+0B0h+var_20], rbx
0x140021a6a  mov     [rbp+0B0h+var_18], ebx
0x140021a70  mov     [rsp+1B0h+var_190], rbx
0x140021a75  call    cs:__imp_RtlQueryRegistryValuesEx
0x140021a7c  nop     dword ptr [rax+rax+00h]
0x140021a81  test    eax, eax
0x140021a83  js      loc_140021B27
0x140021a89  call    cs:__imp_KeEnterCriticalRegion
0x140021a90  nop     dword ptr [rax+rax+00h]
0x140021a95  mov     dl, 1; Wait
0x140021a97  lea     rcx, WPP_MAIN_CB.Queue+10h; Resource
0x140021a9e  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140021aa5  nop     dword ptr [rax+rax+00h]
0x140021aaa  mov     eax, dword ptr [rsp+1B0h+var_180]
0x140021aae  lea     rcx, WPP_MAIN_CB.Queue+10h; Resource
0x140021ab5  movsd   xmm0, qword ptr [rsp+1B0h+var_180+8]
0x140021abb  mov     dword ptr cs:WPP_MAIN_CB.Dpc, eax
0x140021ac1  mov     eax, dword ptr [rsp+1B0h+var_180+4]
0x140021ac5  mov     dword ptr cs:WPP_MAIN_CB.Dpc+4, eax
0x140021acb  mov     eax, dword ptr [rsp+1B0h+var_170]
0x140021acf  mov     dword ptr cs:WPP_MAIN_CB.Dpc.ProcessorHistory, eax
0x140021ad5  mov     al, byte ptr [rsp+1B0h+var_170+4]
0x140021ad9  mov     byte ptr cs:WPP_MAIN_CB.Dpc.ProcessorHistory+4, al
0x140021adf  movzx   eax, word ptr [rsp+1B0h+var_170+5]
0x140021ae4  mov     word ptr cs:WPP_MAIN_CB.Dpc.ProcessorHistory+5, ax
0x140021aeb  mov     al, byte ptr [rsp+1B0h+var_170+7]
0x140021aef  mov     byte ptr cs:WPP_MAIN_CB.Dpc.ProcessorHistory+7, al
0x140021af5  movsd   cs:WPP_MAIN_CB.Dpc.DpcListEntry.Next, xmm0
0x140021afd  call    cs:__imp_ExReleaseResourceLite
0x140021b04  nop     dword ptr [rax+rax+00h]
0x140021b09  call    cs:__imp_KeLeaveCriticalRegion
0x140021b10  nop     dword ptr [rax+rax+00h]
0x140021b15  mov     eax, dword ptr [rsp+1B0h+var_180+4]
0x140021b19  dec     eax
0x140021b1b  cmp     eax, 0FFFFFFFDh
0x140021b1e  ja      short loc_140021B25
0x140021b20  call    AiLogTriggerServiceStartEvent
0x140021b25  mov     eax, ebx
0x140021b27  mov     rcx, [rbp+0B0h+var_10]
0x140021b2e  xor     rcx, rsp; StackCookie
0x140021b31  call    __security_check_cookie
0x140021b36  mov     rbx, [rsp+1B0h+arg_0]
0x140021b3e  add     rsp, 1B0h
0x140021b45  pop     rbp
0x140021b46  retn
```
