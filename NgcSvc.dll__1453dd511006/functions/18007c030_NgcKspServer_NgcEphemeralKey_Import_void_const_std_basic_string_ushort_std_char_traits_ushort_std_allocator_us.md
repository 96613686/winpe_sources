# NgcKspServer::NgcEphemeralKey::Import(void * const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::unique_ptr<NgcUtils::RsaKey,std::default_delete<NgcUtils::RsaKey>>,bool)

- ea: `0x18007c030`
- end: `0x18007c2e4`
- name: `?Import@NgcEphemeralKey@NgcKspServer@@EEAAJQEAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@URsaKey@NgcUtils@@U?$default_delete@URsaKey@NgcUtils@@@std@@@4@_N@Z`
- size: `692`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x18000782c`
- `0x180010a94`
- `0x180011c04`
- `0x180028d18`
- `0x180034960`
- `0x180046d90`
- `0x180048394`
- `0x18004e698`
- `0x18007c030`
- `0x1800cd010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18007c0f7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18007c0f7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18007c22f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18007c22f`
- `ncrypt!NCryptSetProperty` at `0x18007c1fb`
- `ncrypt!NCryptSetProperty` at `0x18007c1fb`
- `ncrypt!NCryptImportKey` at `0x18007c1a3`
- `ncrypt!NCryptImportKey` at `0x18007c29a`
- `ncrypt!NCryptImportKey` at `0x18007c1a3`
- `ncrypt!NCryptImportKey` at `0x18007c29a`

## string_xrefs

- `0x18007c079`: `onecore\ds\security\ngc\kspsvc\svc\ops.cpp`
- `0x18007c1b6`: `onecore\ds\security\ngc\kspsvc\svc\ops.cpp`

## pseudocode

```c

```
