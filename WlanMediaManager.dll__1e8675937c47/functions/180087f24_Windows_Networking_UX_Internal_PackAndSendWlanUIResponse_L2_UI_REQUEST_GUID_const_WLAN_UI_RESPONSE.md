# Windows::Networking::UX::Internal::PackAndSendWlanUIResponse(_L2_UI_REQUEST *,_GUID const &,_WLAN_UI_RESPONSE *)

- ea: `0x180087f24`
- end: `0x1800880ad`
- name: `?PackAndSendWlanUIResponse@Internal@UX@Networking@Windows@@YAJPEAU_L2_UI_REQUEST@@AEBU_GUID@@PEAU_WLAN_UI_RESPONSE@@@Z`
- size: `393`
- prototype: `int(Windows::Networking::UX::Internal *__hidden this, struct _L2_UI_REQUEST *, const struct _GUID *, struct _WLAN_UI_RESPONSE *)`
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18006940c`
- `0x180069574`
- `0x180087d58`

## callees

- `0x180006249`
- `0x18000de4c`
- `0x18001d4d4`
- `0x18002f410`
- `0x18003a070`
- `0x180087f24`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180088098`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180088098`
- `wlanapi!WlanSendUIResponse` at `0x180087ff0`
- `wlanapi!WlanSendUIResponse` at `0x180087ff0`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::Networking::UX::Internal::PackAndSendWlanUIResponse(
        Windows::Networking::UX::Internal *this,
        struct _L2_UI_REQUEST *a2,
        const struct _GUID *a3,
        struct _WLAN_UI_RESPONSE *a4)
{
  unsigned __int64 v7; // r8
  signed int v8; // ebx
  unsigned int v9; // ecx
  int v10; // eax
  PVOID *v11; // rcx
  void *v12; // rcx
  LPVOID *p_pv; // [rsp+20h] [rbp-28h] BYREF
  void *v15; // [rsp+28h] [rbp-20h] BYREF
  char v16; // [rsp+30h] [rbp-18h]
  LPVOID pv; // [rsp+90h] [rbp+48h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_ba28dae9eeea3c6b09312a4c5a49e1a6_Traceguids);
  v7 = (unsigned int)(*(_DWORD *)&a3->Data2 + 72);
  pv = 0;
  p_pv = &pv;
  v15 = 0;
  v16 = 1;
  v8 = CTCoAllocPolicy::Alloc(&pv, 1u, v7, &v15);
  wil::details::out_param_t<wistd::unique_ptr<_L2_UI_RESPONSE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_L2_UI_RESPONSE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>((__int64)&p_pv);
  if ( v8 >= 0 )
  {
    *(_OWORD *)pv = *((_OWORD *)this + 1);
    v9 = *(_DWORD *)&a3->Data2 + 24;
    *((_DWORD *)pv + 8) = v9;
    memcpy_0((char *)pv + 48, a3, v9);
    *((_OWORD *)pv + 1) = *(_OWORD *)a2;
    v10 = WlanSendUIResponse(this, pv);
    v8 = v10;
    if ( v10 > 0 )
      v8 = (unsigned __int16)v10 | 0x80070000;
    if ( v8 < 0 )
    {
      v11 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        goto LABEL_18;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_15;
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        13,
        WPP_ba28dae9eeea3c6b09312a4c5a49e1a6_Traceguids,
        (unsigned int)v8);
    }
    goto LABEL_14;
  }
  v11 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    goto LABEL_18;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_ba28dae9eeea3c6b09312a4c5a49e1a6_Traceguids);
LABEL_14:
    v11 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_15:
  if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 0x40) != 0 )
    WPP_SF_d(v11[2], 15, WPP_ba28dae9eeea3c6b09312a4c5a49e1a6_Traceguids, (unsigned int)v8);
LABEL_18:
  v12 = pv;
  pv = 0;
  if ( v12 )
    CoTaskMemFree(v12);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180087f24  push    rbp
0x180087f26  push    rbx
0x180087f27  push    rsi
0x180087f28  push    rdi
0x180087f29  push    r12
0x180087f2b  push    r14
0x180087f2d  mov     rbp, rsp
0x180087f30  sub     rsp, 48h
0x180087f34  mov     rdi, r8
0x180087f37  mov     r14, rdx
0x180087f3a  mov     rsi, rcx
0x180087f3d  lea     r12, WPP_GLOBAL_Control
0x180087f44  mov     rcx, cs:WPP_GLOBAL_Control
0x180087f4b  cmp     rcx, r12
0x180087f4e  jz      short loc_180087F6B
0x180087f50  test    byte ptr [rcx+1Ch], 40h
0x180087f54  jz      short loc_180087F6B
0x180087f56  mov     edx, 0Ch
0x180087f5b  lea     r8, WPP_ba28dae9eeea3c6b09312a4c5a49e1a6_Traceguids
0x180087f62  mov     rcx, [rcx+10h]
0x180087f66  call    WPP_SF_
0x180087f6b  mov     r8d, [rdi+4]
0x180087f6f  add     r8d, 48h ; 'H'; unsigned __int64
0x180087f73  mov     [rbp+pv], 0
0x180087f7b  lea     rcx, [rbp+pv]; void *
0x180087f7f  mov     [rbp+var_28], rcx
0x180087f83  mov     [rbp+var_20], 0
0x180087f8b  mov     [rbp+var_18], 1
0x180087f8f  lea     r9, [rbp+var_20]; void **
0x180087f93  mov     edx, 1; unsigned int
0x180087f98  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x180087f9d  mov     ebx, eax
0x180087f9f  lea     rcx, [rbp+var_28]
0x180087fa3  call    ??1?$out_param_t@V?$unique_ptr@U_L2_UI_RESPONSE@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_L2_UI_RESPONSE,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_L2_UI_RESPONSE,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x180087fa8  test    ebx, ebx
0x180087faa  js      loc_180088035
0x180087fb0  movups  xmm0, xmmword ptr [rsi+10h]
0x180087fb4  mov     rax, [rbp+pv]
0x180087fb8  movdqu  xmmword ptr [rax], xmm0
0x180087fbc  mov     ecx, [rdi+4]
0x180087fbf  add     ecx, 18h
0x180087fc2  mov     rax, [rbp+pv]
0x180087fc6  mov     [rax+20h], ecx
0x180087fc9  mov     r8d, ecx; Size
0x180087fcc  mov     rcx, [rbp+pv]
0x180087fd0  add     rcx, 30h ; '0'; void *
0x180087fd4  mov     rdx, rdi; Src
0x180087fd7  call    memcpy_0
0x180087fdc  movups  xmm0, xmmword ptr [r14]
0x180087fe0  mov     rax, [rbp+pv]
0x180087fe4  movdqu  xmmword ptr [rax+10h], xmm0
0x180087fe9  mov     rdx, [rbp+pv]
0x180087fed  mov     rcx, rsi
0x180087ff0  call    cs:__imp_WlanSendUIResponse
0x180087ff6  mov     ebx, eax
0x180087ff8  test    eax, eax
0x180087ffa  jle     short loc_180088005
0x180087ffc  movzx   ebx, ax
0x180087fff  or      ebx, 80070000h
0x180088005  test    ebx, ebx
0x180088007  jns     short loc_18008805C
0x180088009  mov     rcx, cs:WPP_GLOBAL_Control
0x180088010  cmp     rcx, r12
0x180088013  jz      short loc_180088087
0x180088015  test    byte ptr [rcx+1Ch], 2
0x180088019  jz      short loc_180088063
0x18008801b  mov     edx, 0Dh
0x180088020  mov     r9d, ebx
0x180088023  lea     r8, WPP_ba28dae9eeea3c6b09312a4c5a49e1a6_Traceguids
0x18008802a  mov     rcx, [rcx+10h]
0x18008802e  call    WPP_SF_d
0x180088033  jmp     short loc_18008805C
0x180088035  mov     rcx, cs:WPP_GLOBAL_Control
0x18008803c  cmp     rcx, r12
0x18008803f  jz      short loc_180088087
0x180088041  test    byte ptr [rcx+1Ch], 2
0x180088045  jz      short loc_180088063
0x180088047  mov     edx, 0Eh
0x18008804c  lea     r8, WPP_ba28dae9eeea3c6b09312a4c5a49e1a6_Traceguids
0x180088053  mov     rcx, [rcx+10h]
0x180088057  call    WPP_SF_
0x18008805c  mov     rcx, cs:WPP_GLOBAL_Control
0x180088063  cmp     rcx, r12
0x180088066  jz      short loc_180088087
0x180088068  test    byte ptr [rcx+1Ch], 40h
0x18008806c  jz      short loc_180088087
0x18008806e  mov     edx, 0Fh
0x180088073  mov     r9d, ebx
0x180088076  lea     r8, WPP_ba28dae9eeea3c6b09312a4c5a49e1a6_Traceguids
0x18008807d  mov     rcx, [rcx+10h]
0x180088081  call    WPP_SF_d
0x180088086  nop
0x180088087  mov     rcx, [rbp+pv]; pv
0x18008808b  mov     [rbp+pv], 0
0x180088093  test    rcx, rcx
0x180088096  jz      short loc_18008809E
0x180088098  call    cs:__imp_CoTaskMemFree
0x18008809e  mov     eax, ebx
0x1800880a0  add     rsp, 48h
0x1800880a4  pop     r14
0x1800880a6  pop     r12
0x1800880a8  pop     rdi
0x1800880a9  pop     rsi
0x1800880aa  pop     rbx
0x1800880ab  pop     rbp
0x1800880ac  retn
```
