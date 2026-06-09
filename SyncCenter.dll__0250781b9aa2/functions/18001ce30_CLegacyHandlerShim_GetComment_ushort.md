# CLegacyHandlerShim::GetComment(ushort * *)

- ea: `0x18001ce30`
- end: `0x18001cf31`
- name: `?GetComment@CLegacyHandlerShim@@UEAAJPEAPEAG@Z`
- size: `257`
- prototype: `__int64 __fastcall(CLegacyHandlerShim *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180007f44`
- `0x18001330c`
- `0x18001ce30`
- `0x18001ec24`
- `0x18004eca8`
- `0x18004ef30`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001cf1e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001cf1e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001cf14`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001cf14`

## pseudocode

```c
__int64 __fastcall CLegacyHandlerShim::GetComment(CLegacyHandlerShim *this, unsigned __int16 **a2)
{
  CLegacyHandlerShim *v2; // rdi
  __int64 v3; // rcx
  int String; // ebx
  __int64 v6; // rax
  __int64 v7; // rdx
  unsigned __int64 v8; // rcx
  unsigned __int64 v9; // r9
  __int64 v11; // [rsp+20h] [rbp-10h]
  __int64 v12; // [rsp+60h] [rbp+30h] BYREF
  HLOCAL hMem; // [rsp+68h] [rbp+38h] BYREF
  LPVOID pv; // [rsp+70h] [rbp+40h] BYREF

  v2 = (CLegacyHandlerShim *)((char *)this - 8);
  *a2 = 0;
  v3 = *((_QWORD *)this + 29);
  v12 = 0;
  String = (*(__int64 (__fastcall **)(__int64, GUID *, GUID *, __int64 *))(*(_QWORD *)v3 + 48LL))(
             v3,
             &GUID_NULL,
             &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99,
             &v12);
  if ( String < 0 )
    goto LABEL_15;
  String = IPropertyStore_GetString(v12, &PKEY_Sync_Comments, a2);
  if ( String < 0 )
    String = -2147467263;
  SafeRelease<ISyncMgrSyncItemContainer>(&v12);
  if ( String < 0 )
  {
LABEL_15:
    if ( !CLegacyHandlerShim::_HasItems(v2) )
    {
      v6 = *(_QWORD *)v2;
      pv = 0;
      String = (*(__int64 (__fastcall **)(CLegacyHandlerShim *, LPVOID *))(v6 + 24))(v2, &pv);
      if ( String >= 0 )
      {
        hMem = 0;
        String = SHFormatResMessageArgAlloc(g_hmodThisDll, 6925, &hMem, pv);
        if ( String >= 0 )
        {
          v9 = -1;
          do
            ++v9;
          while ( *((_WORD *)hMem + v9) );
          String = _AllocStringWorker<CTCoAllocPolicy>(v8, v7, (const unsigned __int16 *)hMem, v9, v11, (void **)a2);
          LocalFree(hMem);
        }
        CoTaskMemFree(pv);
      }
    }
  }
  return (unsigned int)String;
}

```

## disassembly

```asm
0x18001ce30  push    rbp
0x18001ce32  push    rbx
0x18001ce33  push    rsi
0x18001ce34  push    rdi
0x18001ce35  push    r14
0x18001ce37  mov     rbp, rsp
0x18001ce3a  sub     rsp, 30h
0x18001ce3e  xor     r14d, r14d
0x18001ce41  lea     rdi, [rcx-8]
0x18001ce45  mov     [rdx], r14
0x18001ce48  lea     r9, [rbp+arg_0]
0x18001ce4c  mov     rcx, [rdi+0F0h]
0x18001ce53  lea     r8, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99
0x18001ce5a  mov     [rbp+arg_0], r14
0x18001ce5e  mov     rsi, rdx
0x18001ce61  lea     rdx, GUID_NULL
0x18001ce68  mov     rax, [rcx]
0x18001ce6b  mov     rax, [rax+30h]
0x18001ce6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ce74  mov     ebx, eax
0x18001ce76  test    eax, eax
0x18001ce78  js      short loc_18001CEA6
0x18001ce7a  mov     rcx, [rbp+arg_0]
0x18001ce7e  lea     rdx, PKEY_Sync_Comments
0x18001ce85  mov     r8, rsi
0x18001ce88  call    IPropertyStore_GetString
0x18001ce8d  mov     ebx, eax
0x18001ce8f  lea     rcx, [rbp+arg_0]
0x18001ce93  mov     eax, 80004001h
0x18001ce98  test    ebx, ebx
0x18001ce9a  cmovs   ebx, eax
0x18001ce9d  call    ??$SafeRelease@UISyncMgrSyncItemContainer@@@@YAXPEAPEAUISyncMgrSyncItemContainer@@@Z; SafeRelease<ISyncMgrSyncItemContainer>(ISyncMgrSyncItemContainer * *)
0x18001cea2  test    ebx, ebx
0x18001cea4  jns     short loc_18001CF24
0x18001cea6  mov     rcx, rdi; this
0x18001cea9  call    ?_HasItems@CLegacyHandlerShim@@AEBA_NXZ; CLegacyHandlerShim::_HasItems(void)
0x18001ceae  test    al, al
0x18001ceb0  jnz     short loc_18001CF24
0x18001ceb2  mov     rax, [rdi]
0x18001ceb5  lea     rdx, [rbp+pv]
0x18001ceb9  mov     rcx, rdi
0x18001cebc  mov     [rbp+pv], r14
0x18001cec0  mov     rax, [rax+18h]
0x18001cec4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cec9  mov     ebx, eax
0x18001cecb  test    eax, eax
0x18001cecd  js      short loc_18001CF24
0x18001cecf  mov     r9, [rbp+pv]
0x18001ced3  lea     r8, [rbp+hMem]
0x18001ced7  mov     rcx, cs:?g_hmodThisDll@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hmodThisDll
0x18001cede  mov     edx, 1B0Dh
0x18001cee3  mov     [rbp+hMem], r14
0x18001cee7  call    SHFormatResMessageArgAlloc
0x18001ceec  mov     ebx, eax
0x18001ceee  test    eax, eax
0x18001cef0  js      short loc_18001CF1A
0x18001cef2  mov     r8, [rbp+hMem]
0x18001cef6  or      r9, 0FFFFFFFFFFFFFFFFh
0x18001cefa  inc     r9
0x18001cefd  cmp     [r8+r9*2], r14w
0x18001cf02  jnz     short loc_18001CEFA
0x18001cf04  mov     [rsp+30h+var_8], rsi
0x18001cf09  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x18001cf0e  mov     rcx, [rbp+hMem]; hMem
0x18001cf12  mov     ebx, eax
0x18001cf14  call    cs:__imp_LocalFree
0x18001cf1a  mov     rcx, [rbp+pv]; pv
0x18001cf1e  call    cs:__imp_CoTaskMemFree
0x18001cf24  mov     eax, ebx
0x18001cf26  add     rsp, 30h
0x18001cf2a  pop     r14
0x18001cf2c  pop     rdi
0x18001cf2d  pop     rsi
0x18001cf2e  pop     rbx
0x18001cf2f  pop     rbp
0x18001cf30  retn
```
