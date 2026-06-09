# CHandlerItemInfo::NotifyChildSyncTimeSet(_FILETIME const *)

- ea: `0x18001ab10`
- end: `0x18001abd9`
- name: `?NotifyChildSyncTimeSet@CHandlerItemInfo@@UEAAXPEBU_FILETIME@@@Z`
- size: `201`
- prototype: `void(CHandlerItemInfo *__hidden this, const struct _FILETIME *)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000acd0`
- `0x18001ab10`
- `0x18001ac0c`
- `0x18001c5bc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001abd2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ab2d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ab2d`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18001ab90`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18001abaa`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18001ab90`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18001abaa`

## pseudocode

```c
void __fastcall CHandlerItemInfo::NotifyChildSyncTimeSet(LPCRITICAL_SECTION *this, const struct _FILETIME *a2)
{
  LPCRITICAL_SECTION *v2; // rdi
  FILETIME FileTime2; // [rsp+40h] [rbp+8h] BYREF
  FILETIME FileTime1; // [rsp+50h] [rbp+18h] BYREF

  v2 = this - 245;
  EnterCriticalSection(*(this - 242));
  if ( !*((_BYTE *)this - 18) )
  {
    if ( *((_BYTE *)this + 16) )
    {
      FileTime1 = 0;
      CHandlerItemInfo::s_StripSeconds((const struct _FILETIME *)((char *)v2 + 852), &FileTime1);
      FileTime2 = 0;
      CHandlerItemInfo::s_StripSeconds(a2, &FileTime2);
      if ( CompareFileTime(&FileTime1, &FileTime2) )
        CItemInfo::SetIsPartialSync((CItemInfo *)v2, 1);
    }
    else
    {
      CItemInfo::SetIsPartialSync((CItemInfo *)v2, 0);
      *((_BYTE *)this + 16) = 1;
    }
    if ( CompareFileTime((const FILETIME *)((char *)v2 + 852), a2) < 0 )
      CItemInfo::SetLastSyncFinishedTime((CItemInfo *)v2, *a2);
  }
  LeaveCriticalSection(*(this - 242));
}

```

## disassembly

```asm
0x18001ab10  mov     [rsp+arg_8], rbx
0x18001ab15  push    rbp
0x18001ab16  push    rsi
0x18001ab17  push    rdi
0x18001ab18  sub     rsp, 20h
0x18001ab1c  lea     rdi, [rcx-7A8h]
0x18001ab23  mov     rbx, rcx
0x18001ab26  mov     rcx, [rdi+18h]; lpCriticalSection
0x18001ab2a  mov     rsi, rdx
0x18001ab2d  call    cs:__imp_EnterCriticalSection
0x18001ab33  cmp     byte ptr [rbx-12h], 0
0x18001ab37  jnz     loc_18001ABBF
0x18001ab3d  cmp     byte ptr [rbx+10h], 0
0x18001ab41  lea     rbp, [rdi+354h]
0x18001ab48  jnz     short loc_18001AB5A
0x18001ab4a  xor     edx, edx; bool
0x18001ab4c  mov     rcx, rdi; this
0x18001ab4f  call    ?SetIsPartialSync@CItemInfo@@QEAAX_N@Z; CItemInfo::SetIsPartialSync(bool)
0x18001ab54  mov     byte ptr [rbx+10h], 1
0x18001ab58  jmp     short loc_18001ABA4
0x18001ab5a  lea     rdx, [rsp+38h+FileTime1]; struct _FILETIME *
0x18001ab5f  mov     qword ptr [rsp+38h+FileTime1.dwLowDateTime], 0
0x18001ab68  mov     rcx, rbp; struct _FILETIME *
0x18001ab6b  call    ?s_StripSeconds@CHandlerItemInfo@@CAXPEBU_FILETIME@@PEAU2@@Z; CHandlerItemInfo::s_StripSeconds(_FILETIME const *,_FILETIME *)
0x18001ab70  lea     rdx, [rsp+38h+FileTime2]; struct _FILETIME *
0x18001ab75  mov     qword ptr [rsp+38h+FileTime2.dwLowDateTime], 0
0x18001ab7e  mov     rcx, rsi; struct _FILETIME *
0x18001ab81  call    ?s_StripSeconds@CHandlerItemInfo@@CAXPEBU_FILETIME@@PEAU2@@Z; CHandlerItemInfo::s_StripSeconds(_FILETIME const *,_FILETIME *)
0x18001ab86  lea     rdx, [rsp+38h+FileTime2]; lpFileTime2
0x18001ab8b  lea     rcx, [rsp+38h+FileTime1]; lpFileTime1
0x18001ab90  call    cs:__imp_CompareFileTime
0x18001ab96  test    eax, eax
0x18001ab98  jz      short loc_18001ABA4
0x18001ab9a  mov     dl, 1; bool
0x18001ab9c  mov     rcx, rdi; this
0x18001ab9f  call    ?SetIsPartialSync@CItemInfo@@QEAAX_N@Z; CItemInfo::SetIsPartialSync(bool)
0x18001aba4  mov     rdx, rsi; lpFileTime2
0x18001aba7  mov     rcx, rbp; lpFileTime1
0x18001abaa  call    cs:__imp_CompareFileTime
0x18001abb0  test    eax, eax
0x18001abb2  jns     short loc_18001ABBF
0x18001abb4  mov     rdx, [rsi]; struct _FILETIME
0x18001abb7  mov     rcx, rdi; this
0x18001abba  call    ?SetLastSyncFinishedTime@CItemInfo@@QEAAXU_FILETIME@@@Z; CItemInfo::SetLastSyncFinishedTime(_FILETIME)
0x18001abbf  mov     rcx, [rbx-790h]
0x18001abc6  mov     rbx, [rsp+38h+arg_8]
0x18001abcb  add     rsp, 20h
0x18001abcf  pop     rdi
0x18001abd0  pop     rsi
0x18001abd1  pop     rbp
0x18001abd2  jmp     cs:__imp_LeaveCriticalSection
```
