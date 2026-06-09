# CImmersiveWindowFactory::v_Initialize(IImmersiveMonitor *,tagRECT const *)

- ea: `0x180054990`
- end: `0x180054a4e`
- name: `?v_Initialize@CImmersiveWindowFactory@@EEAAJPEAUIImmersiveMonitor@@PEBUtagRECT@@@Z`
- size: `190`
- prototype: `int(CImmersiveWindowFactory *__hidden this, struct IImmersiveMonitor *, const struct tagRECT *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800542a0`
- `0x180054990`
- `0x180056254`
- `0x18005e010`

## import_xrefs

- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x1800549ce`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x1800549ce`

## pseudocode

```c
__int64 __fastcall CImmersiveWindowFactory::v_Initialize(
        CImmersiveWindowFactory *this,
        IUnknown *a2,
        enum ORIENTATION_PREFERENCE *a3)
{
  HRESULT v5; // ebx
  void *ppvOut; // [rsp+50h] [rbp+18h] BYREF

  if ( a3 )
  {
    v5 = 0;
    *(_OWORD *)((char *)this + 116) = *(_OWORD *)a3;
LABEL_7:
    *((_BYTE *)this + 144) = (int)CallerIdentity::GetManifestedOrientationPreference(
                                    *((CallerIdentity **)this + 17),
                                    (unsigned __int16 *)this + 74,
                                    a3) >= 0;
    return (unsigned int)v5;
  }
  ppvOut = 0;
  Microsoft::WRL::ComPtr<IApplicationViewCompatibilityManager>::InternalRelease(&ppvOut);
  v5 = IUnknown_QueryService(a2, &guidService, &GUID_53b23e1b_25e2_4886_9fb6_744b8f15571c, &ppvOut);
  if ( v5 >= 0 )
    v5 = (*(__int64 (__fastcall **)(void *, IUnknown *, _QWORD, _QWORD, char *))(*(_QWORD *)ppvOut + 40LL))(
           ppvOut,
           a2,
           *((_QWORD *)this + 17),
           0,
           (char *)this + 116);
  Microsoft::WRL::ComPtr<IApplicationViewCompatibilityManager>::InternalRelease(&ppvOut);
  if ( v5 >= 0 )
    goto LABEL_7;
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180054990  mov     rax, rsp
0x180054993  mov     [rax+8], rbx
0x180054997  mov     [rax+10h], rsi
0x18005499b  push    rdi
0x18005499c  sub     rsp, 30h
0x1800549a0  mov     rsi, rdx
0x1800549a3  mov     rdi, rcx
0x1800549a6  test    r8, r8
0x1800549a9  jnz     short loc_180054A13
0x1800549ab  lea     rcx, [rax+18h]
0x1800549af  mov     [rax+18h], r8
0x1800549b3  call    ?InternalRelease@?$ComPtr@UIApplicationViewCompatibilityManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IApplicationViewCompatibilityManager>::InternalRelease(void)
0x1800549b8  lea     r9, [rsp+38h+ppvOut]; ppvOut
0x1800549bd  mov     rcx, rsi; punk
0x1800549c0  lea     r8, _GUID_53b23e1b_25e2_4886_9fb6_744b8f15571c; riid
0x1800549c7  lea     rdx, guidService; guidService
0x1800549ce  call    cs:__imp_IUnknown_QueryService
0x1800549d4  mov     ebx, eax
0x1800549d6  test    eax, eax
0x1800549d8  js      short loc_180054A03
0x1800549da  mov     rcx, [rsp+38h+ppvOut]
0x1800549df  lea     rdx, [rdi+74h]
0x1800549e3  mov     r8, [rdi+88h]
0x1800549ea  xor     r9d, r9d
0x1800549ed  mov     [rsp+38h+var_18], rdx
0x1800549f2  mov     rdx, rsi
0x1800549f5  mov     rax, [rcx]
0x1800549f8  mov     rax, [rax+28h]
0x1800549fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054a01  mov     ebx, eax
0x180054a03  lea     rcx, [rsp+38h+ppvOut]
0x180054a08  call    ?InternalRelease@?$ComPtr@UIApplicationViewCompatibilityManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IApplicationViewCompatibilityManager>::InternalRelease(void)
0x180054a0d  test    ebx, ebx
0x180054a0f  js      short loc_180054A3C
0x180054a11  jmp     short loc_180054A1E
0x180054a13  movups  xmm0, xmmword ptr [r8]
0x180054a17  xor     ebx, ebx
0x180054a19  movdqu  xmmword ptr [rcx+74h], xmm0
0x180054a1e  mov     rcx, [rdi+88h]; this
0x180054a25  lea     rdx, [rdi+94h]; unsigned __int16 *
0x180054a2c  call    ?GetManifestedOrientationPreference@CallerIdentity@@YAJPEBGPEAW4ORIENTATION_PREFERENCE@@@Z; CallerIdentity::GetManifestedOrientationPreference(ushort const *,ORIENTATION_PREFERENCE *)
0x180054a31  shr     eax, 1Fh
0x180054a34  xor     al, 1
0x180054a36  mov     [rdi+90h], al
0x180054a3c  mov     rsi, [rsp+38h+arg_8]
0x180054a41  mov     eax, ebx
0x180054a43  mov     rbx, [rsp+38h+arg_0]
0x180054a48  add     rsp, 30h
0x180054a4c  pop     rdi
0x180054a4d  retn
```
