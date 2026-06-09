# CAutoPlayHandlerChooser::~CAutoPlayHandlerChooser(void)

- ea: `0x1800f5604`
- end: `0x1800f56fb`
- name: `??1CAutoPlayHandlerChooser@@UEAA@XZ`
- size: `247`
- prototype: `void __fastcall(CAutoPlayHandlerChooser *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800a4034`
- `0x180193850`

## callees

- `0x180009dd0`
- `0x1800f5604`
- `0x1800f5704`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f564b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f565b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f566e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f5681`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f5694`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f56a7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f56ba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f564b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f565b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f566e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f5681`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f5694`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f56a7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f56ba`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!DestroyWindow` at `0x1800f563b`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!DestroyWindow` at `0x1800f563b`
- `api-ms-win-devices-query-l1-1-0!DevCloseObjectQuery` at `0x1800f5623`
- `api-ms-win-devices-query-l1-1-0!DevCloseObjectQuery` at `0x1800f5623`

## pseudocode

```c
void __fastcall CAutoPlayHandlerChooser::~CAutoPlayHandlerChooser(CAutoPlayHandlerChooser *this)
{
  HWND v2; // rcx

  *(_QWORD *)this = &CAutoPlayHandlerChooser::`vftable';
  if ( *((_QWORD *)this + 36) )
    DevCloseObjectQuery();
  v2 = (HWND)*((_QWORD *)this + 20);
  if ( v2 )
    DestroyWindow(v2);
  CoTaskMemFree(*((LPVOID *)this + 2));
  CoTaskMemFree(*((LPVOID *)this + 3));
  CoTaskMemFree(*((LPVOID *)this + 31));
  CoTaskMemFree(*((LPVOID *)this + 32));
  CoTaskMemFree(*((LPVOID *)this + 33));
  CoTaskMemFree(*((LPVOID *)this + 38));
  CoTaskMemFree(*((LPVOID *)this + 39));
  Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease((char *)this + 240);
  Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease((char *)this + 216);
  Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease((char *)this + 208);
  CSafeElementListenerPtr<DirectUI::Element>::~CSafeElementListenerPtr<DirectUI::Element>((char *)this + 176);
}

```

## disassembly

```asm
0x1800f5604  push    rbx
0x1800f5606  sub     rsp, 20h
0x1800f560a  lea     rax, ??_7CAutoPlayHandlerChooser@@6B@; const CAutoPlayHandlerChooser::`vftable'
0x1800f5611  mov     rbx, rcx
0x1800f5614  mov     [rcx], rax
0x1800f5617  mov     rcx, [rcx+120h]
0x1800f561e  test    rcx, rcx
0x1800f5621  jz      short loc_1800F562F
0x1800f5623  call    cs:__imp_DevCloseObjectQuery
0x1800f562a  nop     dword ptr [rax+rax+00h]
0x1800f562f  mov     rcx, [rbx+0A0h]; hWnd
0x1800f5636  test    rcx, rcx
0x1800f5639  jz      short loc_1800F5647
0x1800f563b  call    cs:__imp_DestroyWindow
0x1800f5642  nop     dword ptr [rax+rax+00h]
0x1800f5647  mov     rcx, [rbx+10h]; pv
0x1800f564b  call    cs:__imp_CoTaskMemFree
0x1800f5652  nop     dword ptr [rax+rax+00h]
0x1800f5657  mov     rcx, [rbx+18h]; pv
0x1800f565b  call    cs:__imp_CoTaskMemFree
0x1800f5662  nop     dword ptr [rax+rax+00h]
0x1800f5667  mov     rcx, [rbx+0F8h]; pv
0x1800f566e  call    cs:__imp_CoTaskMemFree
0x1800f5675  nop     dword ptr [rax+rax+00h]
0x1800f567a  mov     rcx, [rbx+100h]; pv
0x1800f5681  call    cs:__imp_CoTaskMemFree
0x1800f5688  nop     dword ptr [rax+rax+00h]
0x1800f568d  mov     rcx, [rbx+108h]; pv
0x1800f5694  call    cs:__imp_CoTaskMemFree
0x1800f569b  nop     dword ptr [rax+rax+00h]
0x1800f56a0  mov     rcx, [rbx+130h]; pv
0x1800f56a7  call    cs:__imp_CoTaskMemFree
0x1800f56ae  nop     dword ptr [rax+rax+00h]
0x1800f56b3  mov     rcx, [rbx+138h]; pv
0x1800f56ba  call    cs:__imp_CoTaskMemFree
0x1800f56c1  nop     dword ptr [rax+rax+00h]
0x1800f56c6  lea     rcx, [rbx+0F0h]
0x1800f56cd  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1800f56d2  lea     rcx, [rbx+0D8h]
0x1800f56d9  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1800f56de  lea     rcx, [rbx+0D0h]
0x1800f56e5  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1800f56ea  lea     rcx, [rbx+0B0h]
0x1800f56f1  add     rsp, 20h
0x1800f56f5  pop     rbx
0x1800f56f6  jmp     ??1?$CSafeElementListenerPtr@VElement@DirectUI@@@@QEAA@XZ; CSafeElementListenerPtr<DirectUI::Element>::~CSafeElementListenerPtr<DirectUI::Element>(void)
```
