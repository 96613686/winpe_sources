# CFspSynchronousNotifyingChangeApplierTarget::GetSaveActionString(__MIDL___MIDL_itf_synchronization_0000_0000_0001)

- ea: `0x180104658`
- end: `0x18010474b`
- name: `?GetSaveActionString@CFspSynchronousNotifyingChangeApplierTarget@@AEAAPEBGW4__MIDL___MIDL_itf_synchronization_0000_0000_0001@@@Z`
- size: `243`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x180104e80`

## callees

- `0x180104658`

## string_xrefs

- `0x1801046cb`: `SSA_CREATE`
- `0x1801046c3`: `SSA_UPDATE_VERSION_ONLY`
- `0x1801046ab`: `SSA_DELETE_AND_STORE_TOMBSTONE`
- `0x1801046a3`: `SSA_DELETE_AND_REMOVE_TOMBSTONE`
- `0x1801046bb`: `SSA_UPDATE_VERSION_AND_DATA`
- `0x1801046b3`: `SSA_UPDATE_VERSION_AND_MERGE_DATA`
- `0x18010468b`: `SSA_DELETE_CONFLICTING_AND_SAVE_SOURCE_ITEM`
- `0x18010469b`: `SSA_RENAME_SOURCE_AND_UPDATE_VERSION_AND_DATA`
- `0x180104693`: `SSA_RENAME_DESTINATION_AND_UPDATE_VERSION_AND_DATA`
- `0x180104733`: `SSA_CHANGE_ID_UPDATE_VERSION_AND_DELETE_AND_STORE_TOMBSTONE`
- `0x18010472b`: `SSA_CHANGE_ID_UPDATE_VERSION_ONLY`
- `0x180104743`: `SSA_CHANGE_ID_UPDATE_VERSION_AND_MERGE_DATA`
- `0x18010473b`: `SSA_CHANGE_ID_UPDATE_VERSION_AND_SAVE_DATA`
- `0x180104723`: `SSA_CREATE_GHOST`
- `0x180104713`: `SSA_DELETE_GHOST_AND_STORE_TOMBSTONE`
- `0x18010470b`: `SSA_DELETE_GHOST_WITHOUT_TOMBSTONE`

## pseudocode

```c
const wchar_t *__fastcall CFspSynchronousNotifyingChangeApplierTarget::GetSaveActionString(__int64 a1, int a2)
{
  int v2; // edx
  int v3; // edx
  int v4; // edx
  int v5; // edx
  int v6; // edx
  int v7; // edx
  int v8; // edx
  int v10; // edx
  int v11; // edx
  int v12; // edx
  int v13; // edx
  int v14; // edx
  int v15; // edx
  int v16; // edx

  if ( a2 <= 9 )
  {
    if ( a2 == 9 )
      return L"SSA_STORE_MERGE_TOMBSTONE";
    if ( !a2 )
      return L"SSA_CREATE";
    v2 = a2 - 1;
    if ( !v2 )
      return L"SSA_UPDATE_VERSION_ONLY";
    v3 = v2 - 1;
    if ( !v3 )
      return L"SSA_UPDATE_VERSION_AND_DATA";
    v4 = v3 - 1;
    if ( !v4 )
      return L"SSA_UPDATE_VERSION_AND_MERGE_DATA";
    v5 = v4 - 1;
    if ( !v5 )
      return L"SSA_DELETE_AND_STORE_TOMBSTONE";
    v6 = v5 - 1;
    if ( !v6 )
      return L"SSA_DELETE_AND_REMOVE_TOMBSTONE";
    v7 = v6 - 1;
    if ( !v7 )
      return L"SSA_RENAME_SOURCE_AND_UPDATE_VERSION_AND_DATA";
    v8 = v7 - 1;
    if ( !v8 )
      return L"SSA_RENAME_DESTINATION_AND_UPDATE_VERSION_AND_DATA";
    if ( v8 == 1 )
      return L"SSA_DELETE_CONFLICTING_AND_SAVE_SOURCE_ITEM";
    return L"UNKNOWN";
  }
  v10 = a2 - 10;
  if ( !v10 )
    return L"SSA_CHANGE_ID_UPDATE_VERSION_AND_MERGE_DATA";
  v11 = v10 - 1;
  if ( !v11 )
    return L"SSA_CHANGE_ID_UPDATE_VERSION_AND_SAVE_DATA";
  v12 = v11 - 1;
  if ( !v12 )
    return L"SSA_CHANGE_ID_UPDATE_VERSION_AND_DELETE_AND_STORE_TOMBSTONE";
  v13 = v12 - 1;
  if ( !v13 )
    return L"SSA_CHANGE_ID_UPDATE_VERSION_ONLY";
  v14 = v13 - 1;
  if ( !v14 )
    return L"SSA_CREATE_GHOST";
  v15 = v14 - 2;
  if ( !v15 )
    return L"SSA_UNGHOST_ITEM";
  v16 = v15 - 2;
  if ( !v16 )
    return L"SSA_DELETE_GHOST_AND_STORE_TOMBSTONE";
  if ( v16 != 1 )
    return L"UNKNOWN";
  return L"SSA_DELETE_GHOST_WITHOUT_TOMBSTONE";
}

```

## disassembly

```asm
0x180104658  cmp     edx, 9
0x18010465b  jg      short loc_1801046DB
0x18010465d  jz      short loc_1801046D3
0x18010465f  test    edx, edx
0x180104661  jz      short loc_1801046CB
0x180104663  sub     edx, 1
0x180104666  jz      short loc_1801046C3
0x180104668  sub     edx, 1
0x18010466b  jz      short loc_1801046BB
0x18010466d  sub     edx, 1
0x180104670  jz      short loc_1801046B3
0x180104672  sub     edx, 1
0x180104675  jz      short loc_1801046AB
0x180104677  sub     edx, 1
0x18010467a  jz      short loc_1801046A3
0x18010467c  sub     edx, 1
0x18010467f  jz      short loc_18010469B
0x180104681  sub     edx, 1
0x180104684  jz      short loc_180104693
0x180104686  cmp     edx, 1
0x180104689  jnz     short loc_180104703
0x18010468b  lea     rax, aSsaDeleteConfl; "SSA_DELETE_CONFLICTING_AND_SAVE_SOURCE_"...
0x180104692  retn
0x180104693  lea     rax, aSsaRenameDesti; "SSA_RENAME_DESTINATION_AND_UPDATE_VERSI"...
0x18010469a  retn
0x18010469b  lea     rax, aSsaRenameSourc; "SSA_RENAME_SOURCE_AND_UPDATE_VERSION_AN"...
0x1801046a2  retn
0x1801046a3  lea     rax, aSsaDeleteAndRe; "SSA_DELETE_AND_REMOVE_TOMBSTONE"
0x1801046aa  retn
0x1801046ab  lea     rax, aSsaDeleteAndSt; "SSA_DELETE_AND_STORE_TOMBSTONE"
0x1801046b2  retn
0x1801046b3  lea     rax, aSsaUpdateVersi_2; "SSA_UPDATE_VERSION_AND_MERGE_DATA"
0x1801046ba  retn
0x1801046bb  lea     rax, aSsaUpdateVersi; "SSA_UPDATE_VERSION_AND_DATA"
0x1801046c2  retn
0x1801046c3  lea     rax, aSsaUpdateVersi_0; "SSA_UPDATE_VERSION_ONLY"
0x1801046ca  retn
0x1801046cb  lea     rax, aSsaCreate; "SSA_CREATE"
0x1801046d2  retn
0x1801046d3  lea     rax, aSsaStoreMergeT; "SSA_STORE_MERGE_TOMBSTONE"
0x1801046da  retn
0x1801046db  sub     edx, 0Ah
0x1801046de  jz      short loc_180104743
0x1801046e0  sub     edx, 1
0x1801046e3  jz      short loc_18010473B
0x1801046e5  sub     edx, 1
0x1801046e8  jz      short loc_180104733
0x1801046ea  sub     edx, 1
0x1801046ed  jz      short loc_18010472B
0x1801046ef  sub     edx, 1
0x1801046f2  jz      short loc_180104723
0x1801046f4  sub     edx, 2
0x1801046f7  jz      short loc_18010471B
0x1801046f9  sub     edx, 2
0x1801046fc  jz      short loc_180104713
0x1801046fe  cmp     edx, 1
0x180104701  jz      short loc_18010470B
0x180104703  lea     rax, aUnknown_0; "UNKNOWN"
0x18010470a  retn
0x18010470b  lea     rax, aSsaDeleteGhost_0; "SSA_DELETE_GHOST_WITHOUT_TOMBSTONE"
0x180104712  retn
0x180104713  lea     rax, aSsaDeleteGhost; "SSA_DELETE_GHOST_AND_STORE_TOMBSTONE"
0x18010471a  retn
0x18010471b  lea     rax, aSsaUnghostItem; "SSA_UNGHOST_ITEM"
0x180104722  retn
0x180104723  lea     rax, aSsaCreateGhost; "SSA_CREATE_GHOST"
0x18010472a  retn
0x18010472b  lea     rax, aSsaChangeIdUpd_1; "SSA_CHANGE_ID_UPDATE_VERSION_ONLY"
0x180104732  retn
0x180104733  lea     rax, aSsaChangeIdUpd; "SSA_CHANGE_ID_UPDATE_VERSION_AND_DELETE"...
0x18010473a  retn
0x18010473b  lea     rax, aSsaChangeIdUpd_0; "SSA_CHANGE_ID_UPDATE_VERSION_AND_SAVE_D"...
0x180104742  retn
0x180104743  lea     rax, aSsaChangeIdUpd_2; "SSA_CHANGE_ID_UPDATE_VERSION_AND_MERGE_"...
0x18010474a  retn
```
