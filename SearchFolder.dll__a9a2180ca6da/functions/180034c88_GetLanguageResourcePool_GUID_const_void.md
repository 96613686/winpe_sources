# _GetLanguageResourcePool(_GUID const &,void * *)

- ea: `0x180034c88`
- end: `0x180034dc2`
- name: `?_GetLanguageResourcePool@@YAJAEBU_GUID@@PEAPEAX@Z`
- size: `314`
- prototype: `__int64 __fastcall(struct _GUID *, void **, const struct _GUID *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18002ad1c`

## callees

- `0x1800292b8`
- `0x180029dd0`
- `0x18002f540`
- `0x180034a44`
- `0x180034c88`
- `0x180051010`

## import_xrefs

- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x180034d6a`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x180034d6a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180034cfb`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180034cfb`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
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
0x180034c88  mov     [rsp-18h+arg_18], rbx
0x180034c8d  mov     [rsp-18h+arg_0], rcx
0x180034c92  push    rbp
0x180034c93  push    rsi
0x180034c94  push    rdi
0x180034c95  mov     rbp, rsp
0x180034c98  sub     rsp, 30h
0x180034c9c  or      esi, 0FFFFFFFFh
0x180034c9f  mov     qword ptr [rdx], 0
0x180034ca6  cmp     cs:?g_tlsWBCache@@3KA, esi; ulong g_tlsWBCache
0x180034cac  mov     rdi, rdx
0x180034caf  jnz     short loc_180034CB6
0x180034cb1  call    ?DelayAllocateTLS_AllocateInternal@@YAXPEAKPEBG@Z; DelayAllocateTLS_AllocateInternal(ulong *,ushort const *)
0x180034cb6  mov     r9, rdi; void **
0x180034cb9  mov     dword ptr [rbp+arg_0], 0
0x180034cc0  lea     rdx, [rbp+arg_0]; int *
0x180034cc4  call    ?CachedSTAObject_QueryInterface@@YAJKPEAHAEBU_GUID@@PEAPEAX@Z; CachedSTAObject_QueryInterface(ulong,int *,_GUID const &,void * *)
0x180034cc9  mov     r8d, 1; dwClsContext
0x180034ccf  mov     ebx, eax
0x180034cd1  cmp     eax, r8d
0x180034cd4  jnz     loc_180034DB3
0x180034cda  lea     rax, [rbp+arg_10]
0x180034cde  mov     [rbp+arg_10], 0
0x180034ce6  lea     r9, _GUID_b3ddac23_10ba_4407_98de_f5fef5db4629; riid
0x180034ced  mov     [rsp+30h+ppv], rax; ppv
0x180034cf2  xor     edx, edx; pUnkOuter
0x180034cf4  lea     rcx, _GUID_934d4698_6a59_48f8_9f29_9fb30670320e; rclsid
0x180034cfb  call    cs:__imp_CoCreateInstance
0x180034d01  mov     ebx, eax
0x180034d03  test    eax, eax
0x180034d05  js      loc_180034DB3
0x180034d0b  mov     rcx, [rbp+arg_10]
0x180034d0f  lea     r8, [rbp+punk]
0x180034d13  mov     [rbp+punk], 0
0x180034d1b  lea     rdx, _GUID_7b732139_70db_4196_a7ae_5406ed4457c5
0x180034d22  mov     rax, [rcx]
0x180034d25  mov     rax, [rax+50h]
0x180034d29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034d2e  mov     ebx, eax
0x180034d30  test    eax, eax
0x180034d32  js      short loc_180034DA3
0x180034d34  cmp     dword ptr [rbp+arg_0], 0
0x180034d38  jz      short loc_180034D78
0x180034d3a  mov     ecx, cs:?g_tlsWBCache@@3KA; dwTlsIndex
0x180034d40  cmp     ecx, esi
0x180034d42  jz      short loc_180034D78
0x180034d44  mov     rsi, [rbp+punk]
0x180034d48  lea     r8, [rbp+arg_0]; struct CCachedSTAObject **
0x180034d4c  xor     edx, edx; int *
0x180034d4e  mov     [rbp+arg_0], 0
0x180034d56  call    ?_GetCachedSTAObject@@YAJKPEAHPEAPEAVCCachedSTAObject@@@Z; _GetCachedSTAObject(ulong,int *,CCachedSTAObject * *)
0x180034d5b  test    eax, eax
0x180034d5d  js      short loc_180034D78
0x180034d5f  mov     rbx, [rbp+arg_0]
0x180034d63  mov     rdx, rsi; punk
0x180034d66  lea     rcx, [rbx+20h]; ppunk
0x180034d6a  call    cs:__imp_IUnknown_Set
0x180034d70  mov     rcx, rbx; this
0x180034d73  call    ?Release@CCachedSTAObject@@UEAAKXZ; CCachedSTAObject::Release(void)
0x180034d78  mov     rcx, [rbp+punk]
0x180034d7c  lea     rdx, _GUID_7b732139_70db_4196_a7ae_5406ed4457c5
0x180034d83  mov     r8, rdi
0x180034d86  mov     rax, [rcx]
0x180034d89  mov     rax, [rax]
0x180034d8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034d91  mov     rcx, [rbp+punk]
0x180034d95  mov     ebx, eax
0x180034d97  mov     rax, [rcx]
0x180034d9a  mov     rax, [rax+10h]
0x180034d9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034da3  mov     rcx, [rbp+arg_10]
0x180034da7  mov     rax, [rcx]
0x180034daa  mov     rax, [rax+10h]
0x180034dae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034db3  mov     eax, ebx
0x180034db5  mov     rbx, [rsp+30h+arg_18]
0x180034dba  add     rsp, 30h
0x180034dbe  pop     rdi
0x180034dbf  pop     rsi
0x180034dc0  pop     rbp
0x180034dc1  retn
```
