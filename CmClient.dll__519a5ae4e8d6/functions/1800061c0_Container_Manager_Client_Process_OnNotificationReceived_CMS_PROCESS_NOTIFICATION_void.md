# Container::Manager::Client::Process::OnNotificationReceived(_CMS_PROCESS_NOTIFICATION *,void *)

- ea: `0x1800061c0`
- end: `0x1800061fe`
- name: `?OnNotificationReceived@Process@Client@Manager@Container@@CAXPEAU_CMS_PROCESS_NOTIFICATION@@PEAX@Z`
- size: `62`
- prototype: `void __fastcall(struct _CMS_PROCESS_NOTIFICATION *, void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x1800061c0`
- `0x18000700c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800061d8`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800061d8`

## string_xrefs

- `0x1800061ec`: `onecore\base\gendrv\silos\clem\client\dll\CmClientHandles.h`

## pseudocode

```c
void __fastcall Container::Manager::Client::Process::OnNotificationReceived(
        struct _CMS_PROCESS_NOTIFICATION *a1,
        _DWORD *a2)
{
  int v2; // eax
  void *v3; // rcx
  const char *v4; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  a2[6] = *(_DWORD *)a1;
  v2 = *((_DWORD *)a1 + 1);
  v3 = (void *)*((_QWORD *)a2 + 2);
  a2[7] = v2;
  if ( v3 )
  {
    if ( !SetEvent(v3) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0x2AA,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\CmClientHandles.h",
        v4);
  }
}

```

## disassembly

```asm
0x1800061c0  sub     rsp, 28h
0x1800061c4  mov     eax, [rcx]
0x1800061c6  mov     [rdx+18h], eax
0x1800061c9  mov     eax, [rcx+4]
0x1800061cc  mov     rcx, [rdx+10h]; hEvent
0x1800061d0  mov     [rdx+1Ch], eax
0x1800061d3  test    rcx, rcx
0x1800061d6  jz      short loc_1800061E2
0x1800061d8  call    cs:__imp_SetEvent
0x1800061de  test    eax, eax
0x1800061e0  jz      short loc_1800061E7
0x1800061e2  add     rsp, 28h
0x1800061e6  retn
0x1800061e7  mov     rcx, [rsp+28h]; this
0x1800061ec  lea     r8, aOnecoreBaseGen_6; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x1800061f3  mov     edx, 2AAh; void *
0x1800061f8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
