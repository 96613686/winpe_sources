# _GetLanguageResourcePool(_GUID const &,void * *)

- ea: `0x180068848`
- end: `0x180068982`
- name: `?_GetLanguageResourcePool@@YAJAEBU_GUID@@PEAPEAX@Z`
- size: `314`
- prototype: `int(const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180064aa4`

## callees

- `0x18006342c`
- `0x180063afc`
- `0x180066cb0`
- `0x180068498`
- `0x180068848`
- `0x180072010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800688bb`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800688bb`
- `SHCORE!IUnknown_Set` at `0x18006892a`
- `SHCORE!IUnknown_Set` at `0x18006892a`

## pseudocode

```c
__int64 __fastcall _GetLanguageResourcePool(struct _GUID *a1, void **a2, const struct _GUID *a3)
{
  HRESULT Interface; // ebx
  IUnknown *v5; // rsi
  CCachedSTAObject *v6; // rbx
  CCachedSTAObject *v8; // [rsp+50h] [rbp+20h] BYREF
  IUnknown *punk; // [rsp+58h] [rbp+28h] BYREF
  LPVOID ppv; // [rsp+60h] [rbp+30h] BYREF

  v8 = (CCachedSTAObject *)a1;
  *a2 = 0;
  if ( g_tlsWBCache == -1 )
    DelayAllocateTLS_AllocateInternal(&a1->Data1, (const unsigned __int16 *)a2);
  LODWORD(v8) = 0;
  Interface = CachedSTAObject_QueryInterface((unsigned int)a1, (int *)&v8, a3, a2);
  if ( Interface == 1 )
  {
    ppv = 0;
    Interface = CoCreateInstance(
                  &GUID_934d4698_6a59_48f8_9f29_9fb30670320e,
                  0,
                  1u,
                  &GUID_b3ddac23_10ba_4407_98de_f5fef5db4629,
                  &ppv);
    if ( Interface >= 0 )
    {
      punk = 0;
      Interface = (*(__int64 (__fastcall **)(LPVOID, GUID *, IUnknown **))(*(_QWORD *)ppv + 80LL))(
                    ppv,
                    &GUID_7b732139_70db_4196_a7ae_5406ed4457c5,
                    &punk);
      if ( Interface >= 0 )
      {
        if ( (_DWORD)v8 )
        {
          if ( g_tlsWBCache != -1 )
          {
            v5 = punk;
            v8 = 0;
            if ( (int)_GetCachedSTAObject(g_tlsWBCache, 0, &v8) >= 0 )
            {
              v6 = v8;
              IUnknown_Set((IUnknown **)v8 + 4, v5);
              CCachedSTAObject::Release(v6);
            }
          }
        }
        Interface = ((__int64 (__fastcall *)(IUnknown *, GUID *, void **))punk->lpVtbl->QueryInterface)(
                      punk,
                      &GUID_7b732139_70db_4196_a7ae_5406ed4457c5,
                      a2);
        ((void (__fastcall *)(IUnknown *))punk->lpVtbl->Release)(punk);
      }
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    }
  }
  return (unsigned int)Interface;
}

```

## disassembly

```asm
0x180068848  mov     [rsp-18h+arg_18], rbx
0x18006884d  mov     [rsp-18h+arg_0], rcx
0x180068852  push    rbp
0x180068853  push    rsi
0x180068854  push    rdi
0x180068855  mov     rbp, rsp
0x180068858  sub     rsp, 30h
0x18006885c  or      esi, 0FFFFFFFFh
0x18006885f  mov     qword ptr [rdx], 0
0x180068866  cmp     cs:?g_tlsWBCache@@3KA, esi; ulong g_tlsWBCache
0x18006886c  mov     rdi, rdx
0x18006886f  jnz     short loc_180068876
0x180068871  call    ?DelayAllocateTLS_AllocateInternal@@YAXPEAKPEBG@Z; DelayAllocateTLS_AllocateInternal(ulong *,ushort const *)
0x180068876  mov     r9, rdi; void **
0x180068879  mov     dword ptr [rbp+arg_0], 0
0x180068880  lea     rdx, [rbp+arg_0]; int *
0x180068884  call    ?CachedSTAObject_QueryInterface@@YAJKPEAHAEBU_GUID@@PEAPEAX@Z; CachedSTAObject_QueryInterface(ulong,int *,_GUID const &,void * *)
0x180068889  mov     r8d, 1; dwClsContext
0x18006888f  mov     ebx, eax
0x180068891  cmp     eax, r8d
0x180068894  jnz     loc_180068973
0x18006889a  lea     rax, [rbp+arg_10]
0x18006889e  mov     [rbp+arg_10], 0
0x1800688a6  lea     r9, _GUID_b3ddac23_10ba_4407_98de_f5fef5db4629; riid
0x1800688ad  mov     [rsp+30h+ppv], rax; ppv
0x1800688b2  xor     edx, edx; pUnkOuter
0x1800688b4  lea     rcx, _GUID_934d4698_6a59_48f8_9f29_9fb30670320e; rclsid
0x1800688bb  call    cs:__imp_CoCreateInstance
0x1800688c1  mov     ebx, eax
0x1800688c3  test    eax, eax
0x1800688c5  js      loc_180068973
0x1800688cb  mov     rcx, [rbp+arg_10]
0x1800688cf  lea     r8, [rbp+punk]
0x1800688d3  mov     [rbp+punk], 0
0x1800688db  lea     rdx, _GUID_7b732139_70db_4196_a7ae_5406ed4457c5
0x1800688e2  mov     rax, [rcx]
0x1800688e5  mov     rax, [rax+50h]
0x1800688e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800688ee  mov     ebx, eax
0x1800688f0  test    eax, eax
0x1800688f2  js      short loc_180068963
0x1800688f4  cmp     dword ptr [rbp+arg_0], 0
0x1800688f8  jz      short loc_180068938
0x1800688fa  mov     ecx, cs:?g_tlsWBCache@@3KA; dwTlsIndex
0x180068900  cmp     ecx, esi
0x180068902  jz      short loc_180068938
0x180068904  mov     rsi, [rbp+punk]
0x180068908  lea     r8, [rbp+arg_0]; struct CCachedSTAObject **
0x18006890c  xor     edx, edx; int *
0x18006890e  mov     [rbp+arg_0], 0
0x180068916  call    ?_GetCachedSTAObject@@YAJKPEAHPEAPEAVCCachedSTAObject@@@Z; _GetCachedSTAObject(ulong,int *,CCachedSTAObject * *)
0x18006891b  test    eax, eax
0x18006891d  js      short loc_180068938
0x18006891f  mov     rbx, [rbp+arg_0]
0x180068923  mov     rdx, rsi; punk
0x180068926  lea     rcx, [rbx+20h]; ppunk
0x18006892a  call    cs:__imp_IUnknown_Set
0x180068930  mov     rcx, rbx; this
0x180068933  call    ?Release@CCachedSTAObject@@UEAAKXZ; CCachedSTAObject::Release(void)
0x180068938  mov     rcx, [rbp+punk]
0x18006893c  lea     rdx, _GUID_7b732139_70db_4196_a7ae_5406ed4457c5
0x180068943  mov     r8, rdi
0x180068946  mov     rax, [rcx]
0x180068949  mov     rax, [rax]
0x18006894c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068951  mov     rcx, [rbp+punk]
0x180068955  mov     ebx, eax
0x180068957  mov     rax, [rcx]
0x18006895a  mov     rax, [rax+10h]
0x18006895e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068963  mov     rcx, [rbp+arg_10]
0x180068967  mov     rax, [rcx]
0x18006896a  mov     rax, [rax+10h]
0x18006896e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068973  mov     eax, ebx
0x180068975  mov     rbx, [rsp+30h+arg_18]
0x18006897a  add     rsp, 30h
0x18006897e  pop     rdi
0x18006897f  pop     rsi
0x180068980  pop     rbp
0x180068981  retn
```
