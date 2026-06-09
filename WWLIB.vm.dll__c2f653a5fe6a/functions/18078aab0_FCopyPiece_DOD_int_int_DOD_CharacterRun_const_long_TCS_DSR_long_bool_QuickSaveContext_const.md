# FCopyPiece(DOD * *,int,int,DOD *,CharacterRun const *,long,TCS *,DSR *,long *,bool,QuickSaveContext const &)

- ea: `0x18078aab0`
- end: `0x18078b7d1`
- name: `?FCopyPiece@@YA_NPEAPEAVDOD@@HHPEAV1@PEBVCharacterRun@@JPEAUTCS@@PEAUDSR@@PEAJ_NAEBVQuickSaveContext@@@Z`
- size: `3361`
- prototype: `bool __fastcall(struct DOD **, int, int, struct DOD *, const struct CharacterRun *, int, struct TCS *, struct DSR *, int *, bool, const struct QuickSaveContext *)`
- caller_count: `2`
- callee_count: `28`
- tags: ``

## callers

- `0x1808e18a0`
- `0x1809d9668`

## callees

- `0x18005430c`
- `0x18005a320`
- `0x18005a428`
- `0x180073554`
- `0x1800735a4`
- `0x1801932dc`
- `0x1801a0228`
- `0x1801a98f8`
- `0x1801af8e0`
- `0x1801afb4c`
- `0x1801b212c`
- `0x1801e5ab8`
- `0x1801ecbe0`
- `0x180320ce4`
- `0x18078a5c0`
- `0x18078a800`
- `0x18078aab0`
- `0x18078b9e0`
- `0x18078bb90`
- `0x18078d07c`
- `0x18080e040`
- `0x18080f69c`
- `0x180890b6c`
- `0x1808e2214`
- `0x180c218e0`
- `0x1810cc474`
- `0x18129fdb8`
- `0x181519f80`

## import_xrefs

- `KERNEL32!TlsGetValue` at `0x18078aae6`
- `KERNEL32!TlsGetValue` at `0x18078ab86`
- `KERNEL32!TlsGetValue` at `0x18078abaa`
- `KERNEL32!TlsGetValue` at `0x18078abca`
- `KERNEL32!TlsGetValue` at `0x18078abf3`
- `KERNEL32!TlsGetValue` at `0x18078ac08`
- `KERNEL32!TlsGetValue` at `0x18078ac1a`
- `KERNEL32!TlsGetValue` at `0x18078ac5c`
- `KERNEL32!TlsGetValue` at `0x18078acb0`
- `KERNEL32!TlsGetValue` at `0x18078adf9`
- `KERNEL32!TlsGetValue` at `0x18078ae1e`
- `KERNEL32!TlsGetValue` at `0x18078ae4d`
- `KERNEL32!TlsGetValue` at `0x18078aec5`
- `KERNEL32!TlsGetValue` at `0x18078aed4`
- `KERNEL32!TlsGetValue` at `0x18078aee3`
- `KERNEL32!TlsGetValue` at `0x18078b008`
- `KERNEL32!TlsGetValue` at `0x18078b024`
- `KERNEL32!TlsGetValue` at `0x18078b03a`
- `KERNEL32!TlsGetValue` at `0x18078b049`
- `KERNEL32!TlsGetValue` at `0x18078b067`
- `KERNEL32!TlsGetValue` at `0x18078b08d`
- `KERNEL32!TlsGetValue` at `0x18078b0b0`
- `KERNEL32!TlsGetValue` at `0x18078b1a1`
- `KERNEL32!TlsGetValue` at `0x18078b1b0`
- `KERNEL32!TlsGetValue` at `0x18078b1fd`
- `KERNEL32!TlsGetValue` at `0x18078b20c`
- `KERNEL32!TlsGetValue` at `0x18078b21b`
- `KERNEL32!TlsGetValue` at `0x18078b247`
- `KERNEL32!TlsGetValue` at `0x18078b26c`
- `KERNEL32!TlsGetValue` at `0x18078b284`
- `KERNEL32!TlsGetValue` at `0x18078b2bf`
- `KERNEL32!TlsGetValue` at `0x18078b3c0`
- `KERNEL32!TlsGetValue` at `0x18078b44f`
- `KERNEL32!TlsGetValue` at `0x18078b4e8`
- `KERNEL32!TlsGetValue` at `0x18078b627`
- `KERNEL32!TlsGetValue` at `0x18078b69d`
- `KERNEL32!TlsGetValue` at `0x18078b6b7`
- `KERNEL32!TlsGetValue` at `0x18078b6d3`
- `KERNEL32!TlsGetValue` at `0x18078b6e2`
- `KERNEL32!TlsGetValue` at `0x18078b700`
- `KERNEL32!TlsGetValue` at `0x18078b748`
- `KERNEL32!TlsGetValue` at `0x18078b761`
- `KERNEL32!TlsGetValue` at `0x18078b78a`
- `KERNEL32!TlsGetValue` at `0x18078b7ab`
- `KERNEL32!TlsGetValue` at `0x18078aae6`
- `KERNEL32!TlsGetValue` at `0x18078ab86`
- `KERNEL32!TlsGetValue` at `0x18078abaa`
- `KERNEL32!TlsGetValue` at `0x18078abca`
- `KERNEL32!TlsGetValue` at `0x18078abf3`
- `KERNEL32!TlsGetValue` at `0x18078ac08`
- `KERNEL32!TlsGetValue` at `0x18078ac1a`
- `KERNEL32!TlsGetValue` at `0x18078ac5c`
- `KERNEL32!TlsGetValue` at `0x18078acb0`
- `KERNEL32!TlsGetValue` at `0x18078adf9`
- `KERNEL32!TlsGetValue` at `0x18078ae1e`
- `KERNEL32!TlsGetValue` at `0x18078ae4d`
- `KERNEL32!TlsGetValue` at `0x18078aec5`
- `KERNEL32!TlsGetValue` at `0x18078aed4`
- `KERNEL32!TlsGetValue` at `0x18078aee3`
- `KERNEL32!TlsGetValue` at `0x18078b008`
- `KERNEL32!TlsGetValue` at `0x18078b024`
- `KERNEL32!TlsGetValue` at `0x18078b03a`
- `KERNEL32!TlsGetValue` at `0x18078b049`
- `KERNEL32!TlsGetValue` at `0x18078b067`
- `KERNEL32!TlsGetValue` at `0x18078b08d`
- `KERNEL32!TlsGetValue` at `0x18078b0b0`
- `KERNEL32!TlsGetValue` at `0x18078b1a1`
- `KERNEL32!TlsGetValue` at `0x18078b1b0`
- `KERNEL32!TlsGetValue` at `0x18078b1fd`
- `KERNEL32!TlsGetValue` at `0x18078b20c`
- `KERNEL32!TlsGetValue` at `0x18078b21b`
- `KERNEL32!TlsGetValue` at `0x18078b247`
- `KERNEL32!TlsGetValue` at `0x18078b26c`
- `KERNEL32!TlsGetValue` at `0x18078b284`
- `KERNEL32!TlsGetValue` at `0x18078b2bf`
- `KERNEL32!TlsGetValue` at `0x18078b3c0`
- `KERNEL32!TlsGetValue` at `0x18078b44f`
- `KERNEL32!TlsGetValue` at `0x18078b4e8`
- `KERNEL32!TlsGetValue` at `0x18078b627`
- `KERNEL32!TlsGetValue` at `0x18078b69d`
- `KERNEL32!TlsGetValue` at `0x18078b6b7`
- `KERNEL32!TlsGetValue` at `0x18078b6d3`
- `KERNEL32!TlsGetValue` at `0x18078b6e2`
- `KERNEL32!TlsGetValue` at `0x18078b700`
- `KERNEL32!TlsGetValue` at `0x18078b748`
- `KERNEL32!TlsGetValue` at `0x18078b761`
- `KERNEL32!TlsGetValue` at `0x18078b78a`
- `KERNEL32!TlsGetValue` at `0x18078b7ab`

## pseudocode

```c

```
