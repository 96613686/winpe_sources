# InitializeAccountFromDataStoreWithDefaultProvider(Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId &,HSTRING__ * const,ulong,HSTRING__ * const,Windows::Security::Credentials::IWebAccountProvider *,Windows::Security::Credentials::IWebAccount * *)

- ea: `0x18002a790`
- end: `0x18002d93a`
- name: `?InitializeAccountFromDataStoreWithDefaultProvider@@YAJAEAVStoredObjectId@TokenBroker@Authentication@Security@Internal@Windows@@QEAUHSTRING__@@K1PEAUIWebAccountProvider@Credentials@46@PEAPEAUIWebAccount@946@@Z`
- size: `12714`
- prototype: `int(struct Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId *, HSTRING, unsigned int, HSTRING, struct Windows::Security::Credentials::IWebAccountProvider *, struct Windows::Security::Credentials::IWebAccount **)`
- caller_count: `4`
- callee_count: `34`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180028adc`
- `0x180028e44`
- `0x180028f20`
- `0x18005f6c0`

## callees

- `0x180007350`
- `0x18000bd40`
- `0x1800159bc`
- `0x180015a60`
- `0x180015b00`
- `0x18001602c`
- `0x1800168f0`
- `0x180018428`
- `0x18002a3e0`
- `0x18002a790`
- `0x180030a78`
- `0x180030f90`
- `0x180039e90`
- `0x18003a0c0`
- `0x18003a5e0`
- `0x18003ca78`
- `0x180043124`
- `0x1800454f0`
- `0x1800478e8`
- `0x180048ab4`
- `0x1800499b4`
- `0x18004cc00`
- `0x18004e850`
- `0x18004f840`
- `0x180051ff8`
- `0x18005d6c0`
- `0x180071a9c`
- `0x1800722ac`
- `0x1800724cc`
- `0x180072ec0`
- `0x18008e690`
- `0x18008e710`
- `0x180091969`
- `0x18011b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18002c207`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18002c207`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002ac79`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002ad7e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002aea3`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002afe8`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002b19d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002b3ad`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002b51f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002b755`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002b992`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002bd69`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002cb04`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002ac79`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002ad7e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002aea3`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002afe8`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002b19d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002b3ad`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002b51f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002b755`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002b992`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002bd69`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002cb04`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002ac5f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002ad64`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002ae89`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002afce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002b183`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002b393`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002b505`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002b73b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002b978`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002bd4f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002caea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002ac5f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002ad64`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002ae89`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002afce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002b183`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002b393`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002b505`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002b73b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002b978`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002bd4f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002caea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18002c3b0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18002c8b0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18002c3b0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18002c8b0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002a81f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002a832`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002bafd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002ca49`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002d677`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002d689`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002a81f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002a832`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002bafd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002ca49`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002d677`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002d689`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002acbe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002ad18`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002ad28`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002adc3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002add3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002ae2d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002ae3d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002ae4d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002aee8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002aef8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002af08`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002af62`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002af72`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002af82`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002af92`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b057`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b067`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b077`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b087`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b097`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b0f8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b108`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b118`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b128`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b138`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b163`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b20c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b21c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b22c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b23c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b24c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b277`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b287`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b297`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b2a7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b308`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b318`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b328`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b338`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b348`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b373`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b41e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b42e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b43e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b44e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b45e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b492`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b4a2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b4b2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b4c2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b573`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b587`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b597`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b5a7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b5b7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b5fd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b60d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b61d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b62d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b63d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b6a5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b6b8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b6c8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b6d8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b6e8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b6f8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b7a9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b7d8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b7e7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b7f7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b807`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b817`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b827`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b8d3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b8e6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b8f5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b905`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b915`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b925`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b935`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002ba05`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002ba14`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002ba23`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002ba32`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002ba42`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002ba52`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002ba62`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002ba72`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002bb79`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002bb88`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002bb97`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002bba6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002bbb6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002bbc6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002bbd5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002bbe5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002bc54`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002bc63`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002bc72`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002bc82`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002bc92`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002bca2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002bcb2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002bdfa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002be09`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002be18`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002be27`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002be36`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002be46`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002be55`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002be65`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002c02f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002c03e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002c04d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002c05c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002c06b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002c07b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002c08a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002c09a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002c3eb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002c4b0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002c4c0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002c4d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002c4ec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002c515`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002c524`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002c533`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002c542`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002c551`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002c561`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002c570`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002c5cd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002c5e0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002c633`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002c643`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002c69d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002c6ac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002c6bb`

## string_xrefs

- `0x18002c29f`: `onecore\ds\security\tokenbroker\datastore\lib\jsonformat.cpp`
- `0x18002c302`: `onecore\ds\security\tokenbroker\datastore\lib\jsonformat.cpp`
- `0x18002c3c7`: `onecore\ds\security\tokenbroker\datastore\lib\jsonformat.cpp`
- `0x18002aa4e`: `onecore\ds\security\tokenbroker\datastore\lib\account.cpp`
- `0x18002ab63`: `onecore\ds\security\tokenbroker\datastore\lib\account.cpp`
- `0x18002aca3`: `onecore\ds\security\tokenbroker\datastore\lib\account.cpp`
- `0x18002acfd`: `onecore\ds\security\tokenbroker\datastore\lib\account.cpp`
- `0x18002ada8`: `onecore\ds\security\tokenbroker\datastore\lib\account.cpp`
- `0x18002ae12`: `onecore\ds\security\tokenbroker\datastore\lib\account.cpp`
- `0x18002aecd`: `onecore\ds\security\tokenbroker\datastore\lib\account.cpp`
- `0x18002af47`: `onecore\ds\security\tokenbroker\datastore\lib\account.cpp`
- `0x18002b03c`: `onecore\ds\security\tokenbroker\datastore\lib\account.cpp`
- `0x18002b0dd`: `onecore\ds\security\tokenbroker\datastore\lib\account.cpp`
- `0x18002b1f1`: `onecore\ds\security\tokenbroker\datastore\lib\account.cpp`
- `0x18002b2ed`: `onecore\ds\security\tokenbroker\datastore\lib\account.cpp`
- `0x18002b400`: `onecore\ds\security\tokenbroker\datastore\lib\account.cpp`
- `0x18002b5e3`: `onecore\ds\security\tokenbroker\datastore\lib\account.cpp`
- `0x18002b68b`: `onecore\ds\security\tokenbroker\datastore\lib\account.cpp`
- `0x18002b7be`: `onecore\ds\security\tokenbroker\datastore\lib\account.cpp`
- `0x18002b8b9`: `onecore\ds\security\tokenbroker\datastore\lib\account.cpp`
- `0x18002b9e7`: `onecore\ds\security\tokenbroker\datastore\lib\account.cpp`
- `0x18002bb24`: `onecore\ds\security\tokenbroker\datastore\lib\account.cpp`
- `0x18002bd98`: `onecore\ds\security\tokenbroker\datastore\lib\account.cpp`
- `0x18002c5a9`: `onecore\ds\security\tokenbroker\datastore\lib\account.cpp`
- `0x18002c60f`: `onecore\ds\security\tokenbroker\datastore\lib\account.cpp`
- `0x18002c734`: `onecore\ds\security\tokenbroker\datastore\lib\account.cpp`
- `0x18002c8da`: `onecore\ds\security\tokenbroker\datastore\lib\account.cpp`
- `0x18002ca70`: `onecore\ds\security\tokenbroker\datastore\lib\account.cpp`
- `0x18002cb30`: `onecore\ds\security\tokenbroker\datastore\lib\account.cpp`
- `0x18002cc2b`: `onecore\ds\security\tokenbroker\datastore\lib\account.cpp`
- `0x18002ccef`: `onecore\ds\security\tokenbroker\datastore\lib\account.cpp`
- `0x18002cefd`: `onecore\ds\security\tokenbroker\datastore\lib\account.cpp`
- `0x18002cffd`: `onecore\ds\security\tokenbroker\datastore\lib\account.cpp`
- `0x18002d0ca`: `onecore\ds\security\tokenbroker\datastore\lib\account.cpp`
- `0x18002d21c`: `onecore\ds\security\tokenbroker\datastore\lib\account.cpp`
- `0x18002d356`: `onecore\ds\security\tokenbroker\datastore\lib\account.cpp`
- `0x18002d480`: `onecore\ds\security\tokenbroker\datastore\lib\account.cpp`
- `0x18002d578`: `onecore\ds\security\tokenbroker\datastore\lib\account.cpp`
- `0x18002cae3`: `Windows.Internal.Security.Credentials.WebAccountInternal`
- `0x18002b971`: `AccountUserSid`

## pseudocode

```c
// Hidden C++ exception states: #wind=40
__int64 __fastcall InitializeAccountFromDataStoreWithDefaultProvider(
        struct Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId *a1,
        HSTRING a2,
        unsigned int a3,
        HSTRING a4,
        struct Windows::Security::Credentials::IWebAccountProvider *a5,
        struct Windows::Security::Credentials::IWebAccount **a6)
{
  const WCHAR *v9; // rsi
  const WCHAR *v10; // rbx
  PCWSTR StringRawBuffer; // rdi
  PCWSTR v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // rax
  int v15; // eax
  __int64 v16; // rax
  int v17; // eax
  unsigned int v18; // ecx
  int RealIdFromPairwiseId; // eax
  unsigned int v20; // ebx
  int v22; // eax
  unsigned int v23; // ebx
  HSTRING v24; // rbx
  HSTRING v25; // r13
  int SystemDefinedProperty; // eax
  int v27; // edi
  int SingleStringValue; // eax
  int v29; // eax
  int v30; // eax
  int v31; // eax
  int v32; // eax
  int v33; // eax
  int v34; // eax
  int v35; // eax
  int v36; // eax
  int v37; // eax
  int v38; // eax
  int v39; // eax
  int v40; // eax
  HRESULT v41; // eax
  HSTRING v42; // rdi
  int v43; // eax
  int v44; // esi
  HRESULT v45; // eax
  HSTRING v46; // rsi
  int v47; // eax
  int v48; // eax
  unsigned int v49; // r14d
  int v50; // eax
  HSTRING v51; // r14
  unsigned __int16 *v52; // rax
  int v53; // eax
  unsigned int v54; // r15d
  unsigned int v55; // eax
  HSTRING v56; // r15
  const void *v57; // rcx
  int v58; // eax
  unsigned int v59; // r12d
  int InlineBytesValue; // eax
  HLOCAL v61; // r12
  HSTRING v62; // r12
  HSTRING v63; // rax
  HSTRING v64; // r9
  __int64 v65; // r9
  int v66; // r10d
  HSTRING v67; // rax
  _DWORD *v68; // rax
  int v69; // r9d
  _DWORD *v70; // rcx
  HSTRING v71; // rax
  bool v72; // al
  int v73; // eax
  char *v74; // rcx
  __int64 v75; // rdx
  int v76; // eax
  char *v77; // rcx
  char *v78; // rcx
  unsigned int v79; // eax
  int ProviderDefinedPropertyAt; // eax
  HRESULT v81; // eax
  int v82; // eax
  int v83; // eax
  __int64 v84; // rdx
  HRESULT PairwiseIdFromRealId; // eax
  __int64 v86; // rdx
  HSTRING v87; // rcx
  unsigned __int16 *v88; // rax
  signed int v89; // eax
  signed int v90; // eax
  __int64 v91; // rcx
  HSTRING v92; // rcx
  HSTRING v93; // rcx
  HSTRING **v94; // rcx
  HSTRING v95; // rax
  HSTRING v96; // rcx
  signed int v97; // eax
  __int64 v98; // rcx
  HSTRING v99; // rcx
  HSTRING v100; // rcx
  HSTRING **v101; // rcx
  signed int View; // eax
  char *v103; // rcx
  __int64 v104; // rcx
  HSTRING v105; // rcx
  HSTRING v106; // rcx
  HSTRING **v107; // rcx
  signed int v108; // eax
  char *v109; // rcx
  __int64 v110; // rcx
  HSTRING v111; // rcx
  HSTRING v112; // rcx
  HSTRING **v113; // rcx
  char *v114; // rcx
  signed int v115; // eax
  __int64 v116; // rcx
  HSTRING v117; // rcx
  HSTRING v118; // rcx
  HSTRING **v119; // rcx
  signed int v120; // eax
  char *v121; // rcx
  __int64 v122; // rcx
  HSTRING v123; // rcx
  HSTRING v124; // rcx
  HSTRING **v125; // rcx
  signed int v126; // eax
  char *v127; // rcx
  __int64 v128; // rcx
  HSTRING v129; // rcx
  HSTRING v130; // rcx
  HSTRING **v131; // rcx
  char *v132; // rcx
  __int64 v133; // rax
  signed int v134; // eax
  __int64 v135; // rcx
  HSTRING v136; // rcx
  HSTRING v137; // rcx
  HSTRING **v138; // rcx
  __int64 v139; // rax
  HSTRING v140; // rcx
  HSTRING v141; // rcx
  HSTRING **v142; // rcx
  HSTRING v143; // rax
  int UserDataCount; // [rsp+20h] [rbp-E0h]
  int UserDataCounta; // [rsp+20h] [rbp-E0h]
  unsigned int v146; // [rsp+60h] [rbp-A0h] BYREF
  HLOCAL hMem; // [rsp+68h] [rbp-98h] BYREF
  int v148; // [rsp+70h] [rbp-90h]
  HLOCAL v149[2]; // [rsp+78h] [rbp-88h]
  HLOCAL v150; // [rsp+88h] [rbp-78h]
  HSTRING v151; // [rsp+90h] [rbp-70h] BYREF
  char *v152; // [rsp+98h] [rbp-68h] BYREF
  bool v153; // [rsp+A0h] [rbp-60h]
  int v154; // [rsp+A8h] [rbp-58h] BYREF
  char v155; // [rsp+ACh] [rbp-54h]
  HSTRING string[2]; // [rsp+B0h] [rbp-50h]
  HSTRING v157; // [rsp+C0h] [rbp-40h] BYREF
  HSTRING p_hMem; // [rsp+C8h] [rbp-38h] BYREF
  HSTRING v159; // [rsp+D0h] [rbp-30h] BYREF
  HSTRING v160; // [rsp+D8h] [rbp-28h] BYREF
  HSTRING v161; // [rsp+E0h] [rbp-20h] BYREF
  HLOCAL v162; // [rsp+E8h] [rbp-18h] BYREF
  HSTRING v163; // [rsp+F0h] [rbp-10h] BYREF
  HSTRING v164; // [rsp+F8h] [rbp-8h] BYREF
  HSTRING **v165; // [rsp+100h] [rbp+0h] BYREF
  HLOCAL Buf2; // [rsp+108h] [rbp+8h] BYREF
  int v167; // [rsp+110h] [rbp+10h]
  HLOCAL v168[2]; // [rsp+118h] [rbp+18h]
  HLOCAL v169; // [rsp+128h] [rbp+28h]
  HSTRING v170; // [rsp+130h] [rbp+30h] BYREF
  __int64 v171; // [rsp+138h] [rbp+38h] BYREF
  HSTRING v172; // [rsp+140h] [rbp+40h] BYREF
  unsigned int v173; // [rsp+148h] [rbp+48h] BYREF
  char v174; // [rsp+14Ch] [rbp+4Ch] BYREF
  __int64 v175; // [rsp+150h] [rbp+50h] BYREF
  __int64 v176; // [rsp+158h] [rbp+58h] BYREF
  int v177; // [rsp+160h] [rbp+60h]
  __int128 v178; // [rsp+168h] [rbp+68h]
  __int64 v179; // [rsp+178h] [rbp+78h]
  HSTRING newString; // [rsp+180h] [rbp+80h] BYREF
  HSTRING v181; // [rsp+188h] [rbp+88h] BYREF
  HSTRING v182; // [rsp+190h] [rbp+90h]
  int v183; // [rsp+198h] [rbp+98h] BYREF
  int v184; // [rsp+19Ch] [rbp+9Ch] BYREF
  HSTRING v185; // [rsp+1A0h] [rbp+A0h] BYREF
  HSTRING v186; // [rsp+1A8h] [rbp+A8h] BYREF
  struct Windows::Security::Credentials::IWebAccountProvider *v187; // [rsp+1B0h] [rbp+B0h] BYREF
  HSTRING v188; // [rsp+1B8h] [rbp+B8h] BYREF
  HSTRING v189; // [rsp+1C0h] [rbp+C0h] BYREF
  EVENT_DESCRIPTOR v190; // [rsp+1C8h] [rbp+C8h] BYREF
  HLOCAL v191; // [rsp+1D8h] [rbp+D8h]
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+1E0h] [rbp+E0h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+200h] [rbp+100h] BYREF
  __int128 v194; // [rsp+210h] [rbp+110h]
  unsigned int *v195; // [rsp+220h] [rbp+120h]
  __int64 v196; // [rsp+228h] [rbp+128h]
  char **v197; // [rsp+230h] [rbp+130h]
  __int64 v198; // [rsp+238h] [rbp+138h]
  PCWSTR v199; // [rsp+240h] [rbp+140h]
  int v200; // [rsp+248h] [rbp+148h]
  int v201; // [rsp+24Ch] [rbp+14Ch]
  PCWSTR v202; // [rsp+250h] [rbp+150h]
  int v203; // [rsp+258h] [rbp+158h]
  int v204; // [rsp+25Ch] [rbp+15Ch]
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  v182 = a4;
  v146 = a3;
  v181 = a2;
  v187 = a5;
  *(_QWORD *)&v190.Id = a6;
  v9 = (const WCHAR *)*((_QWORD *)a1 + 2);
  if ( (unsigned int)dword_180175000 > 4 )
  {
    v10 = L"NULL";
    if ( a4 )
      StringRawBuffer = WindowsGetStringRawBuffer(a4, 0);
    else
      StringRawBuffer = L"NULL";
    v12 = WindowsGetStringRawBuffer(a2, 0);
    LODWORD(v152) = a3;
    if ( v9 )
      v10 = v9;
    v13 = -1;
    if ( StringRawBuffer )
    {
      v14 = -1;
      do
        ++v14;
      while ( StringRawBuffer[v14] );
      v15 = 2 * v14 + 2;
    }
    else
    {
      StringRawBuffer = &word_1801330B0;
      v15 = 2;
    }
    v202 = StringRawBuffer;
    v203 = v15;
    v204 = 0;
    if ( v12 )
    {
      v16 = -1;
      do
        ++v16;
      while ( v12[v16] );
      v17 = 2 * v16 + 2;
    }
    else
    {
      v12 = &word_1801330B0;
      v17 = 2;
    }
    v199 = v12;
    v200 = v17;
    v201 = 0;
    v197 = &v152;
    v198 = 4;
    if ( v10 )
    {
      do
        ++v13;
      while ( v10[v13] );
      v18 = 2 * v13 + 2;
    }
    else
    {
      v10 = &word_1801330B0;
      v18 = 2;
    }
    v195 = (unsigned int *)v10;
    v196 = v18;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    *(_DWORD *)&EventDescriptor.Level = 4;
    EventDescriptor.Keyword = 0;
    UserData.Ptr = (ULONGLONG)off_180175008;
    UserData.Size = *(unsigned __int16 *)off_180175008;
    UserData.Reserved = 2;
    *(_QWORD *)&v194 = &byte_180158B67;
    *((_QWORD *)&v194 + 1) = 0x10000004ELL;
    LODWORD(v175) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 6u, &UserData);
    a4 = v182;
  }
  hMem = 0;
  v148 = 0;
  *(_OWORD *)v149 = 0;
  v150 = 0;
  p_hMem = (HSTRING)a1;
  if ( (a3 & 1) == 0 )
  {
    RealIdFromPairwiseId = GetRealIdFromPairwiseId(
                             a1,
                             (struct Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId *)&hMem,
                             a2,
                             a4);
    v20 = RealIdFromPairwiseId;
    if ( RealIdFromPairwiseId == -2147024894 )
    {
LABEL_24:
      LocalFree(hMem);
      hMem = 0;
      LocalFree(v149[0]);
      v149[0] = 0;
      LocalFree(v149[1]);
      v149[1] = 0;
      LocalFree(v150);
      return 2147942402LL;
    }
    if ( RealIdFromPairwiseId < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x56F,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\account.cpp",
        (const char *)(unsigned int)RealIdFromPairwiseId,
        UserDataCount);
      LocalFree(hMem);
      hMem = 0;
      LocalFree(v149[0]);
      v149[0] = 0;
      LocalFree(v149[1]);
      v149[1] = 0;
      LocalFree(v150);
      return v20;
    }
    p_hMem = (HSTRING)&hMem;
  }
  v176 = 5;
  v177 = 0;
  v178 = 0;
  v179 = 0;
  v22 = InitializeReaderFromAccountId(
          (Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId **)&p_hMem,
          a2,
          (struct Windows::Internal::Security::Authentication::TokenBroker::JsonObjectReader *)&v176);
  v23 = v22;
  if ( v22 == -2147024894 )
  {
    if ( v179 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v179 + 16LL))(v179);
    if ( *((_QWORD *)&v178 + 1) )
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v178 + 1) + 16LL))(*((_QWORD *)&v178 + 1));
    if ( (_QWORD)v178 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v178 + 16LL))(v178);
    goto LABEL_24;
  }
  if ( v22 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x57A,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\account.cpp",
      (const char *)(unsigned int)v22,
      UserDataCount);
    if ( v179 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v179 + 16LL))(v179);
    if ( *((_QWORD *)&v178 + 1) )
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v178 + 1) + 16LL))(*((_QWORD *)&v178 + 1));
    if ( (_QWORD)v178 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v178 + 16LL))(v178);
LABEL_43:
    LocalFree(hMem);
    hMem = 0;
    LocalFree(v149[0]);
    v149[0] = 0;
    LocalFree(v149[1]);
    v149[1] = 0;
    LocalFree(v150);
    return v23;
  }
  v154 = 5;
  v155 = 0;
  *(_OWORD *)string = 0;
  v161 = 0;
  v151 = 0;
  v164 = 0;
  v185 = 0;
  v186 = 0;
  v183 = 0;
  v184 = 0;
  v24 = 0;
  v188 = 0;
  v25 = 0;
  v189 = 0;
  if ( WindowsCreateStringReference(L"Id", 2u, (HSTRING_HEADER *)&EventDescriptor.Keyword, (HSTRING *)&EventDescriptor) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  SystemDefinedProperty = Windows::Internal::Security::Authentication::TokenBroker::JsonObjectReader::GetSystemDefinedProperty(
                            (Windows::Internal::Security::Authentication::TokenBroker::JsonObjectReader *)&v176,
                            *(HSTRING *)&EventDescriptor.Id,
                            (struct Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty *)&v154);
  v27 = SystemDefinedProperty;
  if ( SystemDefinedProperty < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x58B,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\account.cpp",
      (const char *)(unsigned int)SystemDefinedProperty,
      UserDataCount);
    if ( string[1] )
      WindowsDeleteString(string[1]);
    if ( string[0] )
      (*(void (__fastcall **)(HSTRING))(*(_QWORD *)string[0] + 16LL))(string[0]);
LABEL_772:
    Windows::Internal::Security::Authentication::TokenBroker::JsonObjectReader::~JsonObjectReader((Windows::Internal::Security::Authentication::TokenBroker::JsonObjectReader *)&v176);
    LocalFree(hMem);
    hMem = 0;
    LocalFree(v149[0]);
    v149[0] = 0;
    LocalFree(v149[1]);
    v149[1] = 0;
    LocalFree(v150);
    return (unsigned int)v27;
  }
  SingleStringValue = Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty::GetSingleStringValue(
                        (Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty *)&v154,
                        (struct Windows::Internal::String *)&v161);
  v27 = SingleStringValue;
  if ( SingleStringValue < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x58C,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\account.cpp",
      (const char *)(unsigned int)SingleStringValue,
      UserDataCount);
    if ( v161 )
      WindowsDeleteString(v161);
    if ( string[1] )
      WindowsDeleteString(string[1]);
    if ( string[0] )
      (*(void (__fastcall **)(HSTRING))(*(_QWORD *)string[0] + 16LL))(string[0]);
    goto LABEL_772;
  }
  if ( WindowsCreateStringReference(
         L"Name",
         4u,
         (HSTRING_HEADER *)&EventDescriptor.Keyword,
         (HSTRING *)&EventDescriptor) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v29 = Windows::Internal::Security::Authentication::TokenBroker::JsonObjectReader::GetSystemDefinedProperty(
          (Windows::Internal::Security::Authentication::TokenBroker::JsonObjectReader *)&v176,
          *(HSTRING *)&EventDescriptor.Id,
          (struct Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty *)&v154);
  v27 = v29;
  if ( v29 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x58E,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\account.cpp",
      (const char *)(unsigned int)v29,
      UserDataCount);
    if ( v161 )
      WindowsDeleteString(v161);
    if ( string[1] )
      WindowsDeleteString(string[1]);
    if ( string[0] )
      (*(void (__fastcall **)(HSTRING))(*(_QWORD *)string[0] + 16LL))(string[0]);
    goto LABEL_772;
  }
  v30 = Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty::GetSingleStringValue(
          (Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty *)&v154,
          (struct Windows::Internal::String *)&v151);
  v27 = v30;
  if ( v30 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x58F,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\account.cpp",
      (const char *)(unsigned int)v30,
      UserDataCount);
    if ( v151 )
      WindowsDeleteString(v151);
    if ( v161 )
      WindowsDeleteString(v161);
    if ( string[1] )
      WindowsDeleteString(string[1]);
    if ( string[0] )
      (*(void (__fastcall **)(HSTRING))(*(_QWORD *)string[0] + 16LL))(string[0]);
    goto LABEL_772;
  }
  if ( WindowsCreateStringReference(
         L"ProviderPfn",
         0xBu,
         (HSTRING_HEADER *)&EventDescriptor.Keyword,
         (HSTRING *)&EventDescriptor) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v31 = Windows::Internal::Security::Authentication::TokenBroker::JsonObjectReader::GetSystemDefinedProperty(
          (Windows::Internal::Security::Authentication::TokenBroker::JsonObjectReader *)&v176,
          *(HSTRING *)&EventDescriptor.Id,
          (struct Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty *)&v154);
  v27 = v31;
  if ( v31 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x591,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\account.cpp",
      (const char *)(unsigned int)v31,
      UserDataCount);
    if ( v151 )
      WindowsDeleteString(v151);
    if ( v161 )
      WindowsDeleteString(v161);
    if ( string[1] )
      WindowsDeleteString(string[1]);
    if ( string[0] )
      (*(void (__fastcall **)(HSTRING))(*(_QWORD *)string[0] + 16LL))(string[0]);
    goto LABEL_772;
  }
  v32 = Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty::GetSingleStringValue(
          (Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty *)&v154,
          (struct Windows::Internal::String *)&v164);
  v27 = v32;
  if ( v32 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x592,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\account.cpp",
      (const char *)(unsigned int)v32,
      UserDataCount);
    if ( v164 )
      WindowsDeleteString(v164);
    if ( v151 )
      WindowsDeleteString(v151);
    if ( v161 )
      WindowsDeleteString(v161);
    if ( string[1] )
      WindowsDeleteString(string[1]);
    if ( string[0] )
      (*(void (__fastcall **)(HSTRING))(*(_QWORD *)string[0] + 16LL))(string[0]);
    goto LABEL_772;
  }
  if ( WindowsCreateStringReference(
         L"Scope",
         5u,
         (HSTRING_HEADER *)&EventDescriptor.Keyword,
         (HSTRING *)&EventDescriptor) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v33 = Windows::Internal::Security::Authentication::TokenBroker::JsonObjectReader::GetSystemDefinedProperty(
          (Windows::Internal::Security::Authentication::TokenBroker::JsonObjectReader *)&v176,
          *(HSTRING *)&EventDescriptor.Id,
          (struct Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty *)&v154);
  v27 = v33;
  if ( v33 != -2089484279 )
  {
    if ( v33 < 0 )
    {
      if ( v164 )
        WindowsDeleteString(v164);
      if ( v151 )
        WindowsDeleteString(v151);
      if ( v161 )
        WindowsDeleteString(v161);
      if ( string[1] )
        WindowsDeleteString(string[1]);
      if ( string[0] )
        (*(void (__fastcall **)(HSTRING))(*(_QWORD *)string[0] + 16LL))(string[0]);
      goto LABEL_772;
    }
    v157 = 0;
    v34 = Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty::GetSingleStringValue(
            (Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty *)&v154,
            (struct Windows::Internal::String *)&v157);
    v27 = v34;
    if ( v34 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x59D,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\account.cpp",
        (const char *)(unsigned int)v34,
        UserDataCount);
      if ( v157 )
        WindowsDeleteString(v157);
      if ( v164 )
        WindowsDeleteString(v164);
      if ( v151 )
        WindowsDeleteString(v151);
      if ( v161 )
        WindowsDeleteString(v161);
      if ( string[1] )
        WindowsDeleteString(string[1]);
      if ( string[0] )
        (*(void (__fastcall **)(HSTRING))(*(_QWORD *)string[0] + 16LL))(string[0]);
      goto LABEL_772;
    }
    v35 = ConvertStringScopeToScope(
            (const struct Windows::Internal::String *)&v157,
            (enum Windows::Security::Authentication::Web::Provider::WebAccountScope *)&v183);
    v27 = v35;
    if ( v35 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x59E,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\account.cpp",
        (const char *)(unsigned int)v35,
        UserDataCount);
      if ( v157 )
        WindowsDeleteString(v157);
      if ( v164 )
        WindowsDeleteString(v164);
      if ( v151 )
        WindowsDeleteString(v151);
      if ( v161 )
        WindowsDeleteString(v161);
      if ( string[1] )
        WindowsDeleteString(string[1]);
      if ( string[0] )
        (*(void (__fastcall **)(HSTRING))(*(_QWORD *)string[0] + 16LL))(string[0]);
      goto LABEL_772;
    }
    if ( v157 )
      WindowsDeleteString(v157);
  }
  if ( WindowsCreateStringReference(
         L"EnumerableState",
         0xFu,
         (HSTRING_HEADER *)&EventDescriptor.Keyword,
         (HSTRING *)&EventDescriptor) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v36 = Windows::Internal::Security::Authentication::TokenBroker::JsonObjectReader::GetSystemDefinedProperty(
          (Windows::Internal::Security::Authentication::TokenBroker::JsonObjectReader *)&v176,
          *(HSTRING *)&EventDescriptor.Id,
          (struct Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty *)&v154);
  v27 = v36;
  if ( v36 != -2089484279 )
  {
    if ( v36 < 0 )
    {
      if ( v164 )
        WindowsDeleteString(v164);
      if ( v151 )
        WindowsDeleteString(v151);
      if ( v161 )
        WindowsDeleteString(v161);
      if ( string[1] )
        WindowsDeleteString(string[1]);
      if ( string[0] )
        (*(void (__fastcall **)(HSTRING))(*(_QWORD *)string[0] + 16LL))(string[0]);
      goto LABEL_772;
    }
    v157 = 0;
    v37 = Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty::GetSingleStringValue(
            (Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty *)&v154,
            (struct Windows::Internal::String *)&v157);
    v27 = v37;
    if ( v37 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5AF,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\account.cpp",
        (const char *)(unsigned int)v37,
        UserDataCount);
      if ( v157 )
        WindowsDeleteString(v157);
      if ( v164 )
        WindowsDeleteString(v164);
      if ( v151 )
        WindowsDeleteString(v151);
      if ( v161 )
        WindowsDeleteString(v161);
      if ( string[1] )
        WindowsDeleteString(string[1]);
      if ( string[0] )
        (*(void (__fastcall **)(HSTRING))(*(_QWORD *)string[0] + 16LL))(string[0]);
      goto LABEL_772;
    }
    v38 = ConvertStringEnumerableStateToEnumerableState(
            (const struct Windows::Internal::String *)&v157,
            (enum Windows::Internal::Security::Credentials::WebAccountEnumerableState *)&v184);
    v27 = v38;
    if ( v38 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5B0,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\account.cpp",
        (const char *)(unsigned int)v38,
        UserDataCount);
      if ( v157 )
        WindowsDeleteString(v157);
      if ( v164 )
        WindowsDeleteString(v164);
      if ( v151 )
        WindowsDeleteString(v151);
      if ( v161 )
        WindowsDeleteString(v161);
      if ( string[1] )
        WindowsDeleteString(string[1]);
      if ( string[0] )
        (*(void (__fastcall **)(HSTRING))(*(_QWORD *)string[0] + 16LL))(string[0]);
      goto LABEL_772;
    }
    if ( v157 )
      WindowsDeleteString(v157);
  }
  if ( WindowsCreateStringReference(
         L"PerUserAccountId",
         0x10u,
         (HSTRING_HEADER *)&EventDescriptor.Keyword,
         (HSTRING *)&EventDescriptor) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v39 = Windows::Internal::Security::Authentication::TokenBroker::JsonObjectReader::GetSystemDefinedProperty(
          (Windows::Internal::Security::Authentication::TokenBroker::JsonObjectReader *)&v176,
          *(HSTRING *)&EventDescriptor.Id,
          (struct Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty *)&v154);
  v27 = v39;
  if ( v39 != -2089484279 )
  {
    if ( v39 < 0 )
    {
      if ( v164 )
        WindowsDeleteString(v164);
      if ( v151 )
        WindowsDeleteString(v151);
      if ( v161 )
        WindowsDeleteString(v161);
      if ( string[1] )
        WindowsDeleteString(string[1]);
      if ( string[0] )
        (*(void (__fastcall **)(HSTRING))(*(_QWORD *)string[0] + 16LL))(string[0]);
      goto LABEL_772;
    }
    v40 = Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty::GetSingleStringValue(
            (Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty *)&v154,
            (struct Windows::Internal::String *)&v188);
    v23 = v40;
    if ( v40 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5C0,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\account.cpp",
        (const char *)(unsigned int)v40,
        UserDataCount);
      if ( v188 )
        WindowsDeleteString(v188);
      if ( v164 )
        WindowsDeleteString(v164);
      if ( v151 )
        WindowsDeleteString(v151);
      if ( v161 )
        WindowsDeleteString(v161);
      if ( string[1] )
        WindowsDeleteString(string[1]);
      if ( string[0] )
        (*(void (__fastcall **)(HSTRING))(*(_QWORD *)string[0] + 16LL))(string[0]);
      Windows::Internal::Security::Authentication::TokenBroker::JsonObjectReader::~JsonObjectReader((Windows::Internal::Security::Authentication::TokenBroker::JsonObjectReader *)&v176);
      goto LABEL_43;
    }
    v24 = v188;
  }
  if ( WindowsCreateStringReference(
         L"AccountRevisionNumber",
         0x15u,
         (HSTRING_HEADER *)&EventDescriptor.Keyword,
         (HSTRING *)&EventDescriptor) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v27 = Windows::Internal::Security::Authentication::TokenBroker::JsonObjectReader::GetSystemDefinedProperty(
          (Windows::Internal::Security::Authentication::TokenBroker::JsonObjectReader *)&v176,
          *(HSTRING *)&EventDescriptor.Id,
          (struct Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty *)&v154);
  if ( v27 == -2089484279 )
  {
    v157 = 0;
    v41 = WindowsCreateString(L"0", 1u, &v157);
    v27 = v41;
    if ( v41 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5CF,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\account.cpp",
        (const char *)(unsigned int)v41,
        UserDataCount);
      if ( v24 )
        WindowsDeleteString(v24);
      if ( v164 )
        WindowsDeleteString(v164);
      if ( v151 )
        WindowsDeleteString(v151);
      if ( v161 )
        WindowsDeleteString(v161);
      if ( string[1] )
        WindowsDeleteString(string[1]);
      if ( string[0] )
        (*(void (__fastcall **)(HSTRING))(*(_QWORD *)string[0] + 16LL))(string[0]);
      goto LABEL_772;
    }
    v42 = v157;
    v185 = v157;
    WindowsDeleteString(0);
  }
  else
  {
    if ( v27 < 0 )
    {
      if ( v24 )
        WindowsDeleteString(v24);
      if ( v164 )
        WindowsDeleteString(v164);
      if ( v151 )
        WindowsDeleteString(v151);
      if ( v161 )
        WindowsDeleteString(v161);
      if ( string[1] )
        WindowsDeleteString(string[1]);
      if ( string[0] )
        (*(void (__fastcall **)(HSTRING))(*(_QWORD *)string[0] + 16LL))(string[0]);
      goto LABEL_772;
    }
    v43 = Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty::GetSingleStringValue(
            (Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty *)&v154,
            (struct Windows::Internal::String *)&v185);
    v27 = v43;
    if ( v43 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5D4,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\account.cpp",
        (const char *)(unsigned int)v43,
        UserDataCount);
      if ( v24 )
        WindowsDeleteString(v24);
      if ( v185 )
        WindowsDeleteString(v185);
      if ( v164 )
        WindowsDeleteString(v164);
      if ( v151 )
        WindowsDeleteString(v151);
      if ( v161 )
        WindowsDeleteString(v161);
      if ( string[1] )
        WindowsDeleteString(string[1]);
      if ( string[0] )
        (*(void (__fastcall **)(HSTRING))(*(_QWORD *)string[0] + 16LL))(string[0]);
      goto LABEL_772;
    }
    v42 = v185;
  }
  if ( WindowsCreateStringReference(
         L"AccountPictureRevisionNumber",
         0x1Cu,
         (HSTRING_HEADER *)&EventDescriptor.Keyword,
         (HSTRING *)&EventDescriptor) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v44 = Windows::Internal::Security::Authentication::TokenBroker::JsonObjectReader::GetSystemDefinedProperty(
          (Windows::Internal::Security::Authentication::TokenBroker::JsonObjectReader *)&v176,
          *(HSTRING *)&EventDescriptor.Id,
          (struct Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty *)&v154);
  if ( v44 == -2089484279 )
  {
    v157 = 0;
    v45 = WindowsCreateString(L"0", 1u, &v157);
    v44 = v45;
    if ( v45 >= 0 )
    {
      v46 = v157;
      v186 = v157;
      WindowsDeleteString(0);
      goto LABEL_300;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5E3,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\account.cpp",
      (const char *)(unsigned int)v45,
      UserDataCount);
    if ( v24 )
      WindowsDeleteString(v24);
    if ( v42 )
      WindowsDeleteString(v42);
    if ( v164 )
      WindowsDeleteString(v164);
    if ( v151 )
      WindowsDeleteString(v151);
    if ( v161 )
      WindowsDeleteString(v161);
    if ( string[1] )
      WindowsDeleteString(string[1]);
    if ( string[0] )
      (*(void (__fastcall **)(HSTRING))(*(_QWORD *)string[0] + 16LL))(string[0]);
LABEL_279:
    Windows::Internal::Security::Authentication::TokenBroker::JsonObjectReader::~JsonObjectReader((Windows::Internal::Security::Authentication::TokenBroker::JsonObjectReader *)&v176);
    LocalFree(hMem);
    hMem = 0;
    LocalFree(v149[0]);
    v149[0] = 0;
    LocalFree(v149[1]);
    v149[1] = 0;
    LocalFree(v150);
    return (unsigned int)v44;
  }
  if ( v44 < 0 )
  {
    if ( v24 )
      WindowsDeleteString(v24);
    if ( v42 )
      WindowsDeleteString(v42);
    if ( v164 )
      WindowsDeleteString(v164);
    if ( v151 )
      WindowsDeleteString(v151);
    if ( v161 )
      WindowsDeleteString(v161);
    if ( string[1] )
      WindowsDeleteString(string[1]);
    if ( string[0] )
      (*(void (__fastcall **)(HSTRING))(*(_QWORD *)string[0] + 16LL))(string[0]);
    goto LABEL_279;
  }
  v47 = Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty::GetSingleStringValue(
          (Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty *)&v154,
          (struct Windows::Internal::String *)&v186);
  v44 = v47;
  if ( v47 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5E8,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\account.cpp",
      (const char *)(unsigned int)v47,
      UserDataCount);
    if ( v24 )
      WindowsDeleteString(v24);
    if ( v186 )
      WindowsDeleteString(v186);
    if ( v42 )
      WindowsDeleteString(v42);
    if ( v164 )
      WindowsDeleteString(v164);
    if ( v151 )
      WindowsDeleteString(v151);
    if ( v161 )
      WindowsDeleteString(v161);
    if ( string[1] )
      WindowsDeleteString(string[1]);
    if ( string[0] )
      (*(void (__fastcall **)(HSTRING))(*(_QWORD *)string[0] + 16LL))(string[0]);
    goto LABEL_279;
  }
  v46 = v186;
LABEL_300:
  if ( WindowsCreateStringReference(
         L"AccountUserSid",
         0xEu,
         (HSTRING_HEADER *)&EventDescriptor.Keyword,
         (HSTRING *)&EventDescriptor) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v48 = Windows::Internal::Security::Authentication::TokenBroker::JsonObjectReader::GetSystemDefinedProperty(
          (Windows::Internal::Security::Authentication::TokenBroker::JsonObjectReader *)&v176,
          *(HSTRING *)&EventDescriptor.Id,
          (struct Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty *)&v154);
  v49 = v48;
  if ( v48 != -2089484279 )
  {
    if ( v48 < 0 )
    {
      if ( v24 )
        WindowsDeleteString(v24);
      if ( v46 )
        WindowsDeleteString(v46);
      if ( v42 )
        WindowsDeleteString(v42);
      if ( v164 )
        WindowsDeleteString(v164);
      if ( v151 )
        WindowsDeleteString(v151);
      if ( v161 )
        WindowsDeleteString(v161);
      if ( string[1] )
        WindowsDeleteString(string[1]);
      if ( string[0] )
        (*(void (__fastcall **)(HSTRING))(*(_QWORD *)string[0] + 16LL))(string[0]);
      goto LABEL_323;
    }
    v50 = Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty::GetSingleStringValue(
            (Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty *)&v154,
            (struct Windows::Internal::String *)&v189);
    v49 = v50;
    if ( v50 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5F7,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\account.cpp",
        (const char *)(unsigned int)v50,
        UserDataCount);
      if ( v189 )
        WindowsDeleteString(v189);
      if ( v24 )
        WindowsDeleteString(v24);
      if ( v46 )
        WindowsDeleteString(v46);
      if ( v42 )
        WindowsDeleteString(v42);
      if ( v164 )
        WindowsDeleteString(v164);
      if ( v151 )
        WindowsDeleteString(v151);
      if ( v161 )
        WindowsDeleteString(v161);
      if ( string[1] )
        WindowsDeleteString(string[1]);
      if ( string[0] )
        (*(void (__fastcall **)(HSTRING))(*(_QWORD *)string[0] + 16LL))(string[0]);
LABEL_323:
      Windows::Internal::Security::Authentication::TokenBroker::JsonObjectReader::~JsonObjectReader((Windows::Internal::Security::Authentication::TokenBroker::JsonObjectReader *)&v176);
      LocalFree(hMem);
      hMem = 0;
      LocalFree(v149[0]);
      v149[0] = 0;
      LocalFree(v149[1]);
      v149[1] = 0;
      LocalFree(v150);
      return v49;
    }
    v25 = v189;
  }
  Buf2 = 0;
  v167 = 0;
  *(_OWORD *)v168 = 0;
  v169 = 0;
  v51 = v161;
  v52 = (unsigned __int16 *)WindowsGetStringRawBuffer(v161, 0);
  v53 = Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId::InitializeFromStringId(&Buf2, v52);
  v54 = v53;
  if ( v53 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x606,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\account.cpp",
      (const char *)(unsigned int)v53,
      UserDataCount);
    LocalFree(Buf2);
    Buf2 = 0;
    LocalFree(v168[0]);
    v168[0] = 0;
    LocalFree(v168[1]);
    v168[1] = 0;
    LocalFree(v169);
    v169 = 0;
    if ( v25 )
      WindowsDeleteString(v25);
    if ( v24 )
      WindowsDeleteString(v24);
    if ( v46 )
      WindowsDeleteString(v46);
    if ( v42 )
      WindowsDeleteString(v42);
    if ( v164 )
      WindowsDeleteString(v164);
    if ( v151 )
      WindowsDeleteString(v151);
    if ( v51 )
      WindowsDeleteString(v51);
    if ( string[1] )
      WindowsDeleteString(string[1]);
    if ( string[0] )
      (*(void (__fastcall **)(HSTRING))(*(_QWORD *)string[0] + 16LL))(string[0]);
    Windows::Internal::Security::Authentication::TokenBroker::JsonObjectReader::~JsonObjectReader((Windows::Internal::Security::Authentication::TokenBroker::JsonObjectReader *)&v176);
    LocalFree(hMem);
    hMem = 0;
    LocalFree(v149[0]);
    v149[0] = 0;
    LocalFree(v149[1]);
    v149[1] = 0;
    LocalFree(v150);
    return v54;
  }
  v55 = *((_DWORD *)p_hMem + 2);
  v56 = v164;
  if ( v55 != v167
    || (v57 = *(const void **)p_hMem, *(HLOCAL *)p_hMem != Buf2) && (!v57 || !Buf2 || memcmp_0(v57, Buf2, v55))
    || !ComparePfns(a2, v56) )
  {
    if ( (unsigned int)dword_180175000 > 2 )
    {
      *(_QWORD *)&v190.Id = WindowsGetStringRawBuffer(v56, 0);
      *(_QWORD *)&EventDescriptor.Id = WindowsGetStringRawBuffer(v51, 0);
      v146 = -2147023092;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        &dword_180175000,
        byte_1801589A9,
        0);
    }
    LocalFree(Buf2);
    Buf2 = 0;
    LocalFree(v168[0]);
    v168[0] = 0;
    LocalFree(v168[1]);
    v168[1] = 0;
    LocalFree(v169);
    v169 = 0;
    if ( v25 )
      WindowsDeleteString(v25);
    if ( v24 )
      WindowsDeleteString(v24);
    if ( v46 )
      WindowsDeleteString(v46);
    if ( v42 )
      WindowsDeleteString(v42);
    if ( v56 )
      WindowsDeleteString(v56);
    if ( v151 )
      WindowsDeleteString(v151);
    if ( v51 )
      WindowsDeleteString(v51);
    if ( string[1] )
      WindowsDeleteString(string[1]);
    if ( string[0] )
      (*(void (__fastcall **)(HSTRING))(*(_QWORD *)string[0] + 16LL))(string[0]);
    goto LABEL_744;
  }
  v191 = 0;
  v173 = 0;
  if ( WindowsCreateStringReference(
         L"IdSalt",
         6u,
         (HSTRING_HEADER *)&EventDescriptor.Keyword,
         (HSTRING *)&EventDescriptor) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v58 = Windows::Internal::Security::Authentication::TokenBroker::JsonObjectReader::GetSystemDefinedProperty(
          (Windows::Internal::Security::Authentication::TokenBroker::JsonObjectReader *)&v176,
          *(HSTRING *)&EventDescriptor.Id,
          (struct Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty *)&v154);
  v59 = v58;
  if ( v58 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x61E,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\account.cpp",
      (const char *)(unsigned int)v58,
      UserDataCount);
    LocalFree(Buf2);
    Buf2 = 0;
    LocalFree(v168[0]);
    v168[0] = 0;
    LocalFree(v168[1]);
    v168[1] = 0;
    LocalFree(v169);
    v169 = 0;
    if ( v25 )
      WindowsDeleteString(v25);
    if ( v24 )
      WindowsDeleteString(v24);
    if ( v46 )
      WindowsDeleteString(v46);
    if ( v42 )
      WindowsDeleteString(v42);
    if ( v56 )
      WindowsDeleteString(v56);
    if ( v151 )
      WindowsDeleteString(v151);
    if ( v51 )
      WindowsDeleteString(v51);
    if ( string[1] )
      WindowsDeleteString(string[1]);
    if ( string[0] )
      (*(void (__fastcall **)(HSTRING))(*(_QWORD *)string[0] + 16LL))(string[0]);
LABEL_389:
    Windows::Internal::Security::Authentication::TokenBroker::JsonObjectReader::~JsonObjectReader((Windows::Internal::Security::Authentication::TokenBroker::JsonObjectReader *)&v176);
    LocalFree(hMem);
    hMem = 0;
    LocalFree(v149[0]);
    v149[0] = 0;
    LocalFree(v149[1]);
    v149[1] = 0;
    LocalFree(v150);
    return v59;
  }
  v162 = 0;
  InlineBytesValue = Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty::GetInlineBytesValue(
                       (Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty *)&v154,
                       (unsigned __int8 **)&v162,
                       &v173);
  v59 = InlineBytesValue;
  if ( InlineBytesValue < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x61F,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\account.cpp",
      (const char *)(unsigned int)InlineBytesValue,
      UserDataCount);
    LocalFree(Buf2);
    Buf2 = 0;
    LocalFree(v168[0]);
    v168[0] = 0;
    LocalFree(v168[1]);
    v168[1] = 0;
    LocalFree(v169);
    v169 = 0;
    if ( v25 )
      WindowsDeleteString(v25);
    if ( v24 )
      WindowsDeleteString(v24);
    if ( v46 )
      WindowsDeleteString(v46);
    if ( v42 )
      WindowsDeleteString(v42);
    if ( v56 )
      WindowsDeleteString(v56);
    if ( v151 )
      WindowsDeleteString(v151);
    if ( v51 )
      WindowsDeleteString(v51);
    if ( string[1] )
      WindowsDeleteString(string[1]);
    if ( string[0] )
      (*(void (__fastcall **)(HSTRING))(*(_QWORD *)string[0] + 16LL))(string[0]);
    goto LABEL_389;
  }
  v61 = v162;
  v191 = v162;
  if ( v173 != 32 )
  {
    if ( (unsigned int)dword_180175000 > 2 )
    {
      v146 = -2147023092;
      v195 = &v146;
      v196 = 4;
      *(_DWORD *)&v190.Id = 184549376;
      *(_DWORD *)&v190.Level = 2;
      v190.Keyword = 0;
      UserData.Ptr = (ULONGLONG)off_180175008;
      UserData.Size = *(unsigned __int16 *)off_180175008;
      UserData.Reserved = 2;
      *(_QWORD *)&v194 = byte_18015896D;
      *((_QWORD *)&v194 + 1) = 0x10000003BLL;
      LODWORD(v152) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(RegHandle, &v190, 0, 0, 3u, &UserData);
    }
    if ( v61 )
      LocalFree(v61);
    LocalFree(Buf2);
    Buf2 = 0;
    LocalFree(v168[0]);
    v168[0] = 0;
    LocalFree(v168[1]);
    v168[1] = 0;
    LocalFree(v169);
    v169 = 0;
    if ( v25 )
      WindowsDeleteString(v25);
    if ( v24 )
      WindowsDeleteString(v24);
    if ( v46 )
      WindowsDeleteString(v46);
    if ( v42 )
      WindowsDeleteString(v42);
    if ( v56 )
      WindowsDeleteString(v56);
    if ( v151 )
      WindowsDeleteString(v151);
    if ( v51 )
      WindowsDeleteString(v51);
    if ( string[1] )
      WindowsDeleteString(string[1]);
    if ( string[0] )
      (*(void (__fastcall **)(HSTRING))(*(_QWORD *)string[0] + 16LL))(string[0]);
LABEL_744:
    Windows::Internal::Security::Authentication::TokenBroker::JsonObjectReader::~JsonObjectReader((Windows::Internal::Security::Authentication::TokenBroker::JsonObjectReader *)&v176);
    LocalFree(hMem);
    hMem = 0;
    LocalFree(v149[0]);
    v149[0] = 0;
    LocalFree(v149[1]);
    v149[1] = 0;
    LocalFree(v150);
    return 2147944204LL;
  }
  v153 = AccountPropertiesAccessCheck(
           v146,
           v182,
           (struct Windows::Internal::Security::Authentication::TokenBroker::JsonObjectReader *)&v176);
  p_hMem = 0;
  v62 = 0;
  *(_QWORD *)&EventDescriptor.Id = 0;
  v174 = 0;
  v160 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileHashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0>>::InternalRelease(&v160);
  v160 = 0;
  v63 = (HSTRING)operator new(0xC0u, (const struct std::nothrow_t *)std::nothrow);
  v157 = v63;
  if ( !v63 )
    goto LABEL_687;
  *(_QWORD *)v63 = &Windows::Foundation::Collections::IMap<HSTRING__ *,HSTRING__ *>::`vftable';
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *>,Microsoft::WRL::FtmBase>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *>,Microsoft::WRL::FtmBase>(v63 + 2);
  v64 = v157;
  *((_QWORD *)v157 + 8) = 1;
  *(_QWORD *)v64 = &Microsoft::WRL::RuntimeClass<Windows::Foundation::Collections::IMap<HSTRING__ *,HSTRING__ *>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::Collections::IMap<HSTRING__ *,HSTRING__ *>'};
  *((_QWORD *)v64 + 1) = &Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *>,Microsoft::WRL::FtmBase>'};
  *((_QWORD *)v64 + 2) = &Microsoft::WRL::RuntimeClass<Windows::Foundation::Collections::IMap<HSTRING__ *,HSTRING__ *>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *>'};
  *((_QWORD *)v64 + 3) = &Microsoft::WRL::RuntimeClass<Windows::Foundation::Collections::IMap<HSTRING__ *,HSTRING__ *>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
  {
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    v64 = v157;
  }
  *(_QWORD *)v64 = &Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::`vftable'{for `Windows::Foundation::Collections::IMap<HSTRING__ *,HSTRING__ *>'};
  *((_QWORD *)v64 + 1) = &Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *>,Microsoft::WRL::FtmBase>'};
  *((_QWORD *)v64 + 2) = &Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::`vftable'{for `Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *>'};
  *((_QWORD *)v64 + 3) = &Microsoft::WRL::RuntimeClass<Windows::Foundation::Collections::IMap<HSTRING__ *,HSTRING__ *>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  *((_QWORD *)v64 + 9) = v64;
  *((_QWORD *)v64 + 10) = 0;
  *((_QWORD *)v64 + 11) = 0;
  *((_DWORD *)v64 + 24) = 17;
  *((_QWORD *)v64 + 14) = 0xFFFFFFFFLL;
  *((_QWORD *)v64 + 15) = 0;
  *((_DWORD *)v64 + 32) = 0;
  *((_DWORD *)v64 + 33) = 10;
  *((_QWORD *)v64 + 17) = 0;
  *((_QWORD *)v64 + 18) = 0;
  *((_DWORD *)v64 + 25) = 1061158912;
  *((_DWORD *)v64 + 26) = 1048576000;
  *((_DWORD *)v64 + 27) = 1074790400;
  XWinRT::XHashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::KeyTraits,XWinRT::CElementTraits<HSTRING__ *>>::UpdateRehashThresholds();
  *(_DWORD *)(v65 + 160) = v66;
  InitializeSRWLock((PSRWLOCK)(v65 + 168));
  v67 = v157;
  *((_QWORD *)v157 + 22) = 0;
  *((_BYTE *)v67 + 184) = 0;
  *((_DWORD *)v67 + 47) = 0;
  v68 = operator new(4u, (const struct std::nothrow_t *)std::nothrow);
  v70 = v68;
  if ( !v68 )
  {
    v143 = v157;
    *((_QWORD *)v157 + 22) = 0;
    (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v143 + 16LL))(v143);
LABEL_687:
    v59 = -2147024882;
    v75 = 1593;
LABEL_688:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v75,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\account.cpp",
      (const char *)v59,
      UserDataCount);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileHashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0>>::InternalRelease(&v160);
    if ( v162 )
      LocalFree(v162);
    LocalFree(Buf2);
    Buf2 = 0;
    LocalFree(v168[0]);
    v168[0] = 0;
    LocalFree(v168[1]);
    v168[1] = 0;
    LocalFree(v169);
    v169 = 0;
    if ( v25 )
      WindowsDeleteString(v25);
    if ( v24 )
      WindowsDeleteString(v24);
    if ( v46 )
      WindowsDeleteString(v46);
    if ( v42 )
      WindowsDeleteString(v42);
    if ( v56 )
      WindowsDeleteString(v56);
    if ( v151 )
      WindowsDeleteString(v151);
    if ( v51 )
      WindowsDeleteString(v51);
    Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty::~JsonObjectProperty((Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty *)&v154);
    goto LABEL_389;
  }
  *v68 = 1;
  v71 = v157;
  *((_QWORD *)v157 + 22) = v70;
  *((_BYTE *)v71 + 184) = 1;
  v160 = v71;
  v72 = v153;
  if ( !v153 )
    goto LABEL_440;
  LODWORD(v175) = 0;
  v152 = 0;
  v73 = (***((__int64 (__fastcall ****)(_QWORD, GUID *, char **))&v178 + 1))(
          *((_QWORD *)&v178 + 1),
          &GUID_d44662bc_dce3_59a8_9272_4b210f33908b,
          &v152);
  v173 = v73;
  if ( v73 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4C4,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\jsonformat.cpp",
      (const char *)(unsigned int)v73,
      UserDataCount);
    v74 = v152;
    if ( v152 )
    {
      v152 = 0;
      (*(void (__fastcall **)(char *))(*(_QWORD *)v74 + 16LL))(v74);
    }
    v59 = v173;
    v75 = 1597;
    goto LABEL_688;
  }
  v76 = (*(__int64 (__fastcall **)(char *, __int64 *))(*(_QWORD *)v152 + 56LL))(v152, &v175);
  v173 = v76;
  if ( v76 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4C5,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\jsonformat.cpp",
      (const char *)(unsigned int)v76,
      UserDataCount);
    v77 = v152;
    if ( v152 )
    {
      v152 = 0;
      (*(void (__fastcall **)(char *))(*(_QWORD *)v77 + 16LL))(v77);
    }
    v59 = v173;
    v75 = 1597;
    goto LABEL_688;
  }
  v173 = v175;
  v78 = v152;
  if ( v152 )
  {
    v152 = 0;
    (*(void (__fastcall **)(char *))(*(_QWORD *)v78 + 16LL))(v78);
  }
  v79 = 0;
  LODWORD(v175) = 0;
  if ( !v173 )
  {
LABEL_439:
    v72 = v153;
LABEL_440:
    v172 = 0;
    v170 = 0;
    if ( (v146 & 2) != 0 )
    {
      if ( !v72 )
      {
        if ( (unsigned int)dword_180175000 > 2 )
        {
          v146 = -2147024891;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
            (unsigned int)&dword_180175000,
            (unsigned int)&word_180158A86,
            0,
            v69,
            (__int64)&v146);
        }
        if ( v170 )
          WindowsDeleteString(v170);
        if ( v172 )
          WindowsDeleteString(v172);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileHashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0>>::~ComPtr<Windows::Foundation::Collections::Internal::AgileHashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0>>(&v160);
        if ( v62 )
          WindowsDeleteString(v62);
        if ( p_hMem )
          WindowsDeleteString(p_hMem);
        if ( v162 )
          LocalFree(v162);
        Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId::InternalRelease((Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId *)&Buf2);
        if ( v25 )
          WindowsDeleteString(v25);
        if ( v24 )
          WindowsDeleteString(v24);
        if ( v46 )
          WindowsDeleteString(v46);
        if ( v42 )
          WindowsDeleteString(v42);
        if ( v56 )
          WindowsDeleteString(v56);
        if ( v151 )
          WindowsDeleteString(v151);
        if ( v51 )
          WindowsDeleteString(v51);
        Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty::~JsonObjectProperty((Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty *)&v154);
        Windows::Internal::Security::Authentication::TokenBroker::JsonObjectReader::~JsonObjectReader((Windows::Internal::Security::Authentication::TokenBroker::JsonObjectReader *)&v176);
        Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId::InternalRelease((Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId *)&hMem);
        return 2147942405LL;
      }
      if ( v168[0] )
      {
        PairwiseIdFromRealId = Windows::Internal::String::_InitializeHelper(
                                 (Windows::Internal::String *)&v172,
                                 (const unsigned __int16 *)v168[0]);
        v146 = PairwiseIdFromRealId;
        if ( PairwiseIdFromRealId >= 0 )
        {
          WindowsDeleteString(v170);
          v170 = 0;
          PairwiseIdFromRealId = WindowsDuplicateString(v24, &v170);
          v146 = PairwiseIdFromRealId;
          if ( PairwiseIdFromRealId < 0 )
          {
            v86 = 1640;
LABEL_527:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v86,
              (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\account.cpp",
              (const char *)(unsigned int)PairwiseIdFromRealId,
              UserDataCount);
            goto LABEL_528;
          }
          goto LABEL_559;
        }
      }
      else
      {
        PairwiseIdFromRealId = -2147467261;
        v146 = -2147467261;
      }
      v86 = 1637;
      goto LABEL_527;
    }
    PairwiseIdFromRealId = GetPairwiseIdFromRealId(
                             (struct Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId *)&Buf2,
                             (struct Windows::Internal::String *)&v172,
                             v181,
                             v182);
    v146 = PairwiseIdFromRealId;
    if ( PairwiseIdFromRealId < 0 )
    {
      v86 = 1649;
      goto LABEL_527;
    }
    if ( !WindowsIsStringEmpty(v24) )
    {
      UserData.Ptr = 0;
      UserData.Size = 0;
      v194 = 0;
      v195 = 0;
      v88 = (unsigned __int16 *)WindowsGetStringRawBuffer(v24, 0);
      v89 = Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId::InitializeFromStringId(
              (HLOCAL *)&UserData,
              v88);
      v146 = v89;
      if ( v89 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x67B,
          (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\account.cpp",
          (const char *)(unsigned int)v89,
          UserDataCount);
        Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId::InternalRelease((Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId *)&UserData);
        goto LABEL_528;
      }
      GetPairwiseIdFromRealId(
        (struct Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId *)&UserData,
        (struct Windows::Internal::String *)&v170,
        v181,
        v182);
      Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId::InternalRelease((Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId *)&UserData);
    }
LABEL_559:
    v165 = 0;
    v159 = 0;
    v163 = 0;
    v171 = 0;
    if ( WindowsCreateStringReference(
           L"Windows.Internal.Security.Credentials.WebAccountInternal",
           0x38u,
           (HSTRING_HEADER *)&UserData.Size,
           (HSTRING *)&UserData) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    v90 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::Security::Credentials::IWebAccountInternalFactory>>(
            UserData.Ptr,
            &v165);
    v146 = v90;
    if ( v90 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x691,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\account.cpp",
        (const char *)(unsigned int)v90,
        UserDataCount);
      v91 = v171;
      if ( v171 )
      {
        v171 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v91 + 16LL))(v91);
      }
      v92 = v163;
      if ( v163 )
      {
        v163 = 0;
        (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v92 + 16LL))(v92);
      }
      v93 = v159;
      if ( v159 )
      {
        v159 = 0;
        (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v93 + 16LL))(v93);
      }
      v94 = v165;
      if ( v165 )
      {
        v165 = 0;
        ((void (__fastcall *)(HSTRING **))(*v94)[2])(v94);
      }
      goto LABEL_528;
    }
    v95 = (HSTRING)v165;
    v181 = (HSTRING)v165;
    newString = **v165;
    v96 = v159;
    if ( v159 )
    {
      v159 = 0;
      (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v96 + 16LL))(v96);
      v95 = v181;
    }
    v97 = ((__int64 (__fastcall *)(HSTRING, GUID *, HSTRING *))newString)(
            v95,
            &GUID_414f1885_ae5f_4340_a5de_2e39df0c8605,
            &v159);
    v146 = v97;
    if ( v97 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x692,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\account.cpp",
        (const char *)(unsigned int)v97,
        UserDataCount);
      v98 = v171;
      if ( v171 )
      {
        v171 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v98 + 16LL))(v98);
      }
      v99 = v163;
      if ( v163 )
      {
        v163 = 0;
        (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v99 + 16LL))(v99);
      }
      v100 = v159;
      if ( v159 )
      {
        v159 = 0;
        (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v100 + 16LL))(v100);
      }
      v101 = v165;
      if ( v165 )
      {
        v165 = 0;
        ((void (__fastcall *)(HSTRING **))(*v101)[2])(v101);
      }
LABEL_528:
      if ( v170 )
        WindowsDeleteString(v170);
      if ( v172 )
        WindowsDeleteString(v172);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileHashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0>>::~ComPtr<Windows::Foundation::Collections::Internal::AgileHashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0>>(&v160);
      if ( v62 )
        WindowsDeleteString(v62);
      if ( p_hMem )
        WindowsDeleteString(p_hMem);
      if ( v162 )
        LocalFree(v162);
      Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId::InternalRelease((Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId *)&Buf2);
      if ( v25 )
        WindowsDeleteString(v25);
      if ( v24 )
        WindowsDeleteString(v24);
      if ( v46 )
        WindowsDeleteString(v46);
      if ( v42 )
        WindowsDeleteString(v42);
      if ( v56 )
        WindowsDeleteString(v56);
      v87 = v151;
      if ( !v151 )
        goto LABEL_550;
      goto LABEL_549;
    }
    if ( v153 )
    {
      v152 = 0;
      View = Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::GetView(
               v157,
               &v152);
      v146 = View;
      if ( View < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x698,
          (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\account.cpp",
          (const char *)(unsigned int)View,
          UserDataCount);
        v103 = v152;
        if ( v152 )
        {
          v152 = 0;
          (*(void (__fastcall **)(char *))(*(_QWORD *)v103 + 16LL))(v103);
        }
        v104 = v171;
        if ( v171 )
        {
          v171 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v104 + 16LL))(v104);
        }
        v105 = v163;
        if ( v163 )
        {
          v163 = 0;
          (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v105 + 16LL))(v105);
        }
        v106 = v159;
        if ( v159 )
        {
          v159 = 0;
          (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v106 + 16LL))(v106);
        }
        v107 = v165;
        if ( v165 )
        {
          v165 = 0;
          ((void (__fastcall *)(HSTRING **))(*v107)[2])(v107);
        }
LABEL_595:
        if ( v170 )
          WindowsDeleteString(v170);
        if ( v172 )
          WindowsDeleteString(v172);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileHashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0>>::~ComPtr<Windows::Foundation::Collections::Internal::AgileHashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0>>(&v160);
        if ( v62 )
          WindowsDeleteString(v62);
        if ( p_hMem )
          WindowsDeleteString(p_hMem);
        if ( v162 )
          LocalFree(v162);
        Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId::InternalRelease((Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId *)&Buf2);
        if ( v25 )
          WindowsDeleteString(v25);
        if ( v24 )
          WindowsDeleteString(v24);
        if ( v46 )
          WindowsDeleteString(v46);
        if ( v42 )
          WindowsDeleteString(v42);
        if ( v56 )
          WindowsDeleteString(v56);
        if ( !v151 )
          goto LABEL_550;
        v87 = v151;
LABEL_549:
        WindowsDeleteString(v87);
LABEL_550:
        if ( v51 )
          WindowsDeleteString(v51);
        Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty::~JsonObjectProperty((Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty *)&v154);
        Windows::Internal::Security::Authentication::TokenBroker::JsonObjectReader::~JsonObjectReader((Windows::Internal::Security::Authentication::TokenBroker::JsonObjectReader *)&v176);
        Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId::InternalRelease((Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId *)&hMem);
        return v146;
      }
      newString = v159;
      v182 = *(HSTRING *)(*(_QWORD *)v159 + 48LL);
      v181 = (HSTRING)&v163;
      Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::Security::Credentials::IWebAccountInternal>>::operator Windows::Internal::Security::Credentials::IWebAccountInternal * *(&v181);
      UserDataCounta = (int)v172;
      v108 = ((__int64 (__fastcall *)(HSTRING, struct Windows::Security::Credentials::IWebAccountProvider *, HSTRING, _QWORD))v182)(
               newString,
               v187,
               v151,
               0);
      v146 = v108;
      if ( v108 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x6A5,
          (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\account.cpp",
          (const char *)(unsigned int)v108,
          UserDataCounta);
        v109 = v152;
        if ( v152 )
        {
          v152 = 0;
          (*(void (__fastcall **)(char *))(*(_QWORD *)v109 + 16LL))(v109);
        }
        v110 = v171;
        if ( v171 )
        {
          v171 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v110 + 16LL))(v110);
        }
        v111 = v163;
        if ( v163 )
        {
          v163 = 0;
          (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v111 + 16LL))(v111);
        }
        v112 = v159;
        if ( v159 )
        {
          v159 = 0;
          (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v112 + 16LL))(v112);
        }
        v113 = v165;
        if ( v165 )
        {
          v165 = 0;
          ((void (__fastcall *)(HSTRING **))(*v113)[2])(v113);
        }
        goto LABEL_595;
      }
      v114 = v152;
      if ( v152 )
      {
        v152 = 0;
        (*(void (__fastcall **)(char *))(*(_QWORD *)v114 + 16LL))(v114);
      }
    }
    else
    {
      v175 = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileHashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0>>::InternalRelease(&v175);
      v115 = Windows::Foundation::Collections::Internal::AgileHashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0>::Make(&v175);
      v146 = v115;
      if ( v115 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x6AD,
          (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\account.cpp",
          (const char *)(unsigned int)v115,
          UserDataCount);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileHashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0>>::~ComPtr<Windows::Foundation::Collections::Internal::AgileHashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0>>(&v175);
        v116 = v171;
        if ( v171 )
        {
          v171 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v116 + 16LL))(v116);
        }
        v117 = v163;
        if ( v163 )
        {
          v163 = 0;
          (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v117 + 16LL))(v117);
        }
        v118 = v159;
        if ( v159 )
        {
          v159 = 0;
          (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v118 + 16LL))(v118);
        }
        v119 = v165;
        if ( v165 )
        {
          v165 = 0;
          ((void (__fastcall *)(HSTRING **))(*v119)[2])(v119);
        }
        goto LABEL_595;
      }
      v152 = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v152);
      v120 = Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::GetView(
               v175,
               &v152);
      v146 = v120;
      if ( v120 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x6AF,
          (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\account.cpp",
          (const char *)(unsigned int)v120,
          UserDataCount);
        v121 = v152;
        if ( v152 )
        {
          v152 = 0;
          (*(void (__fastcall **)(char *))(*(_QWORD *)v121 + 16LL))(v121);
        }
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileHashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0>>::~ComPtr<Windows::Foundation::Collections::Internal::AgileHashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0>>(&v175);
        v122 = v171;
        if ( v171 )
        {
          v171 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v122 + 16LL))(v122);
        }
        v123 = v163;
        if ( v163 )
        {
          v163 = 0;
          (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v123 + 16LL))(v123);
        }
        v124 = v159;
        if ( v159 )
        {
          v159 = 0;
          (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v124 + 16LL))(v124);
        }
        v125 = v165;
        if ( v165 )
        {
          v165 = 0;
          ((void (__fastcall *)(HSTRING **))(*v125)[2])(v125);
        }
        goto LABEL_595;
      }
      newString = v159;
      v182 = *(HSTRING *)(*(_QWORD *)v159 + 48LL);
      v181 = (HSTRING)&v163;
      Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::Security::Credentials::IWebAccountInternal>>::operator Windows::Internal::Security::Credentials::IWebAccountInternal * *(&v181);
      UserDataCounta = (int)v172;
      v126 = ((__int64 (__fastcall *)(HSTRING, struct Windows::Security::Credentials::IWebAccountProvider *, _QWORD, _QWORD))v182)(
               newString,
               v187,
               0,
               0);
      v146 = v126;
      if ( v126 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x6BB,
          (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\account.cpp",
          (const char *)(unsigned int)v126,
          UserDataCounta);
        v127 = v152;
        if ( v152 )
        {
          v152 = 0;
          (*(void (__fastcall **)(char *))(*(_QWORD *)v127 + 16LL))(v127);
        }
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileHashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0>>::~ComPtr<Windows::Foundation::Collections::Internal::AgileHashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0>>(&v175);
        v128 = v171;
        if ( v171 )
        {
          v171 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v128 + 16LL))(v128);
        }
        v129 = v163;
        if ( v163 )
        {
          v163 = 0;
          (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v129 + 16LL))(v129);
        }
        v130 = v159;
        if ( v159 )
        {
          v159 = 0;
          (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v130 + 16LL))(v130);
        }
        v131 = v165;
        if ( v165 )
        {
          v165 = 0;
          ((void (__fastcall *)(HSTRING **))(*v131)[2])(v131);
        }
        goto LABEL_595;
      }
      v132 = v152;
      if ( v152 )
      {
        v152 = 0;
        (*(void (__fastcall **)(char *))(*(_QWORD *)v132 + 16LL))(v132);
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileHashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0>>::~ComPtr<Windows::Foundation::Collections::Internal::AgileHashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0>>(&v175);
    }
    v181 = v163;
    newString = *(HSTRING *)(*(_QWORD *)v163 + 48LL);
    v187 = (struct Windows::Security::Credentials::IWebAccountProvider *)&v171;
    v133 = Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::Security::Credentials::IWebAccountInternal>>::operator Windows::Internal::Security::Credentials::IWebAccountInternal * *(&v187);
    v134 = ((__int64 (__fastcall *)(HSTRING, __int64))newString)(v181, v133);
    v146 = v134;
    if ( v134 >= 0 )
    {
      v139 = v171;
      v171 = 0;
      **(_QWORD **)&v190.Id = v139;
      v140 = v163;
      if ( v163 )
      {
        v163 = 0;
        (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v140 + 16LL))(v140);
      }
      v141 = v159;
      if ( v159 )
      {
        v159 = 0;
        (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v141 + 16LL))(v141);
      }
      v142 = v165;
      if ( v165 )
      {
        v165 = 0;
        ((void (__fastcall *)(HSTRING **))(*v142)[2])(v142);
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6BE,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\account.cpp",
        (const char *)(unsigned int)v134,
        UserDataCounta);
      v135 = v171;
      if ( v171 )
      {
        v171 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v135 + 16LL))(v135);
      }
      v136 = v163;
      if ( v163 )
      {
        v163 = 0;
        (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v136 + 16LL))(v136);
      }
      v137 = v159;
      if ( v159 )
      {
        v159 = 0;
        (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v137 + 16LL))(v137);
      }
      v138 = v165;
      if ( v165 )
      {
        v165 = 0;
        ((void (__fastcall *)(HSTRING **))(*v138)[2])(v138);
      }
    }
    goto LABEL_595;
  }
  while ( 1 )
  {
    ProviderDefinedPropertyAt = Windows::Internal::Security::Authentication::TokenBroker::JsonObjectReader::GetProviderDefinedPropertyAt(
                                  (Windows::Internal::Security::Authentication::TokenBroker::JsonObjectReader *)&v176,
                                  v79,
                                  (struct Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty *)&v154);
    LODWORD(v152) = ProviderDefinedPropertyAt;
    if ( ProviderDefinedPropertyAt < 0 )
      break;
    newString = 0;
    v81 = WindowsDuplicateString(string[1], &newString);
    LODWORD(v152) = v81;
    if ( v81 >= 0 )
    {
      *(_QWORD *)&EventDescriptor.Id = newString;
      WindowsDeleteString(v62);
      v62 = *(HSTRING *)&EventDescriptor.Id;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1C4,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\jsonformat.cpp",
        (const char *)(unsigned int)v81,
        UserDataCount);
    }
    ProviderDefinedPropertyAt = (int)v152;
    if ( (int)v152 < 0 )
    {
      v84 = 1601;
      goto LABEL_500;
    }
    v82 = Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty::GetSingleStringValue(
            (Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty *)&v154,
            (struct Windows::Internal::String *)&p_hMem);
    LODWORD(v152) = v82;
    if ( v82 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x642,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\account.cpp",
        (const char *)(unsigned int)v82,
        UserDataCount);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileHashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0>>::InternalRelease(&v160);
      if ( v62 )
        WindowsDeleteString(v62);
      if ( p_hMem )
        WindowsDeleteString(p_hMem);
      if ( v162 )
        LocalFree(v162);
      LocalFree(Buf2);
      Buf2 = 0;
      LocalFree(v168[0]);
      v168[0] = 0;
      LocalFree(v168[1]);
      v168[1] = 0;
      LocalFree(v169);
      v169 = 0;
      goto LABEL_483;
    }
    v83 = Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::Insert(
            v157,
            v62,
            p_hMem,
            &v174);
    LODWORD(v152) = v83;
    if ( v83 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x646,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\account.cpp",
        (const char *)(unsigned int)v83,
        UserDataCount);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileHashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0>>::~ComPtr<Windows::Foundation::Collections::Internal::AgileHashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0>>(&v160);
      if ( v62 )
        WindowsDeleteString(v62);
      if ( p_hMem )
        WindowsDeleteString(p_hMem);
      if ( v162 )
        LocalFree(v162);
      Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId::InternalRelease((Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId *)&Buf2);
LABEL_483:
      if ( v25 )
        WindowsDeleteString(v25);
      if ( v24 )
        WindowsDeleteString(v24);
      if ( v46 )
        WindowsDeleteString(v46);
      if ( v42 )
        WindowsDeleteString(v42);
      if ( v56 )
        WindowsDeleteString(v56);
      if ( v151 )
        WindowsDeleteString(v151);
      if ( v51 )
        WindowsDeleteString(v51);
      Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty::~JsonObjectProperty((Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty *)&v154);
      Windows::Internal::Security::Authentication::TokenBroker::JsonObjectReader::~JsonObjectReader((Windows::Internal::Security::Authentication::TokenBroker::JsonObjectReader *)&v176);
      Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId::InternalRelease((Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId *)&hMem);
      return (unsigned int)v152;
    }
    v79 = v175 + 1;
    LODWORD(v175) = v79;
    if ( v79 >= v173 )
      goto LABEL_439;
  }
  v84 = 1600;
LABEL_500:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v84,
    (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\account.cpp",
    (const char *)(unsigned int)ProviderDefinedPropertyAt,
    UserDataCount);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileHashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0>>::InternalRelease(&v160);
  if ( v62 )
    WindowsDeleteString(v62);
  if ( p_hMem )
    WindowsDeleteString(p_hMem);
  if ( v162 )
    LocalFree(v162);
  LocalFree(Buf2);
  Buf2 = 0;
  LocalFree(v168[0]);
  v168[0] = 0;
  LocalFree(v168[1]);
  v168[1] = 0;
  LocalFree(v169);
  v169 = 0;
  if ( v25 )
    WindowsDeleteString(v25);
  if ( v24 )
    WindowsDeleteString(v24);
  if ( v46 )
    WindowsDeleteString(v46);
  if ( v42 )
    WindowsDeleteString(v42);
  if ( v56 )
    WindowsDeleteString(v56);
  if ( v151 )
    WindowsDeleteString(v151);
  if ( v51 )
    WindowsDeleteString(v51);
  Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty::~JsonObjectProperty((Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty *)&v154);
  Windows::Internal::Security::Authentication::TokenBroker::JsonObjectReader::~JsonObjectReader((Windows::Internal::Security::Authentication::TokenBroker::JsonObjectReader *)&v176);
  LocalFree(hMem);
  hMem = 0;
  LocalFree(v149[0]);
  v149[0] = 0;
  LocalFree(v149[1]);
  v149[1] = 0;
  LocalFree(v150);
  return (unsigned int)v152;
}

```

## disassembly

```asm
0x18002a790  mov     [rsp-8+arg_10], rbx
0x18002a795  push    rbp
0x18002a796  push    rsi
0x18002a797  push    rdi
0x18002a798  push    r12
0x18002a79a  push    r13
0x18002a79c  push    r14
0x18002a79e  push    r15
0x18002a7a0  lea     rbp, [rsp-170h]
0x18002a7a8  sub     rsp, 270h
0x18002a7af  mov     rax, cs:__security_cookie
0x18002a7b6  xor     rax, rsp
0x18002a7b9  mov     [rbp+1A0h+var_40], rax
0x18002a7c0  mov     [rbp+1A0h+var_110], r9
0x18002a7c7  mov     r15d, r8d
0x18002a7ca  mov     [rsp+2A0h+var_240], r8d
0x18002a7cf  mov     r12, rdx
0x18002a7d2  mov     [rbp+1A0h+var_118], rdx
0x18002a7d9  mov     r14, rcx
0x18002a7dc  mov     rax, [rbp+1A0h+arg_20]
0x18002a7e3  mov     [rbp+1A0h+var_F0], rax
0x18002a7ea  mov     rax, [rbp+1A0h+arg_28]
0x18002a7f1  mov     qword ptr [rbp+1A0h+var_D8.Id], rax
0x18002a7f8  mov     rsi, [rcx+10h]
0x18002a7fc  mov     eax, cs:dword_180175000
0x18002a802  xor     r13d, r13d
0x18002a805  cmp     eax, 4
0x18002a808  jbe     loc_18002A9C0
0x18002a80e  lea     rbx, aNull_1; "NULL"
0x18002a815  test    r9, r9
0x18002a818  jz      short loc_18002A82A
0x18002a81a  xor     edx, edx; length
0x18002a81c  mov     rcx, r9; string
0x18002a81f  call    cs:__imp_WindowsGetStringRawBuffer
0x18002a825  mov     rdi, rax
0x18002a828  jmp     short loc_18002A82D
0x18002a82a  mov     rdi, rbx
0x18002a82d  xor     edx, edx; length
0x18002a82f  mov     rcx, r12; string
0x18002a832  call    cs:__imp_WindowsGetStringRawBuffer
0x18002a838  mov     rdx, rax
0x18002a83b  mov     dword ptr [rbp+1A0h+var_208], r15d
0x18002a83f  test    rsi, rsi
0x18002a842  cmovnz  rbx, rsi
0x18002a846  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18002a84d  test    rdi, rdi
0x18002a850  jz      short loc_18002A869
0x18002a852  mov     rax, rcx
0x18002a855  lea     rax, [rax+1]
0x18002a859  cmp     [rdi+rax*2], r13w
0x18002a85e  jnz     short loc_18002A855
0x18002a860  lea     eax, ds:2[rax*2]
0x18002a867  jmp     short loc_18002A875
0x18002a869  lea     rdi, word_1801330B0
0x18002a870  mov     eax, 2
0x18002a875  mov     [rbp+1A0h+var_50], rdi
0x18002a87c  mov     [rbp+1A0h+var_48], eax
0x18002a882  mov     [rbp+1A0h+var_44], r13d
0x18002a889  test    rdx, rdx
0x18002a88c  jz      short loc_18002A8A5
0x18002a88e  mov     rax, rcx
0x18002a891  lea     rax, [rax+1]
0x18002a895  cmp     [rdx+rax*2], r13w
0x18002a89a  jnz     short loc_18002A891
0x18002a89c  lea     eax, ds:2[rax*2]
0x18002a8a3  jmp     short loc_18002A8B1
0x18002a8a5  lea     rdx, word_1801330B0
0x18002a8ac  mov     eax, 2
0x18002a8b1  mov     [rbp+1A0h+var_60], rdx
0x18002a8b8  mov     [rbp+1A0h+var_58], eax
0x18002a8be  mov     [rbp+1A0h+var_54], r13d
0x18002a8c5  lea     rax, [rbp+1A0h+var_208]
0x18002a8c9  mov     [rbp+1A0h+var_70], rax
0x18002a8d0  mov     [rbp+1A0h+var_68], 4
0x18002a8db  test    rbx, rbx
0x18002a8de  jz      short loc_18002A8F4
0x18002a8e0  lea     rcx, [rcx+1]
0x18002a8e4  cmp     [rbx+rcx*2], r13w
0x18002a8e9  jnz     short loc_18002A8E0
0x18002a8eb  lea     ecx, ds:2[rcx*2]
0x18002a8f2  jmp     short loc_18002A900
0x18002a8f4  lea     rbx, word_1801330B0
0x18002a8fb  mov     ecx, 2
0x18002a900  mov     [rbp+1A0h+var_80], rbx
0x18002a907  mov     dword ptr [rbp+1A0h+var_78], ecx
0x18002a90d  mov     dword ptr [rbp+1A0h+var_78+4], r13d
0x18002a914  mov     dword ptr [rbp+1A0h+EventDescriptor.Id], 0B000000h
0x18002a91e  movzx   eax, cs:word_180158B5D
0x18002a925  mov     dword ptr [rbp+1A0h+EventDescriptor.Level], eax
0x18002a92b  mov     [rbp+1A0h+EventDescriptor.Keyword], r13
0x18002a932  mov     rax, cs:off_180175008
0x18002a939  mov     [rbp+1A0h+var_A0.Ptr], rax
0x18002a940  movzx   eax, word ptr [rax]
0x18002a943  mov     [rbp+1A0h+var_A0.Size], eax
0x18002a949  mov     dword ptr [rbp+1A0h+var_A0.0Ch], 2
0x18002a953  lea     rax, byte_180158B67
0x18002a95a  mov     qword ptr [rbp+1A0h+var_90], rax
0x18002a961  mov     dword ptr [rbp+1A0h+var_90+8], 4Eh ; 'N'
0x18002a96b  mov     dword ptr [rbp+1A0h+var_90+0Ch], 1
0x18002a975  lea     rax, _TraceLoggingMetadataEnd
0x18002a97c  lea     rcx, _TraceLoggingMetadata
0x18002a983  sub     eax, ecx
0x18002a985  mov     dword ptr [rbp+1A0h+var_150], eax
0x18002a988  mov     eax, dword ptr [rbp+1A0h+var_150]
0x18002a98b  lea     rax, [rbp+1A0h+var_A0]
0x18002a992  mov     [rsp+2A0h+UserData], rax; UserData
0x18002a997  mov     [rsp+2A0h+UserDataCount], 6; int
0x18002a99f  xor     r9d, r9d; RelatedActivityId
0x18002a9a2  xor     r8d, r8d; ActivityId
0x18002a9a5  lea     rdx, [rbp+1A0h+EventDescriptor]; EventDescriptor
0x18002a9ac  mov     rcx, cs:RegHandle; RegHandle
0x18002a9b3  call    cs:__imp_EventWriteTransfer
0x18002a9b9  mov     r9, [rbp+1A0h+var_110]; HSTRING
0x18002a9c0  mov     [rsp+2A0h+hMem], r13
0x18002a9c5  mov     [rsp+2A0h+var_230], r13d
0x18002a9ca  xorps   xmm0, xmm0
0x18002a9cd  movdqu  xmmword ptr [rsp+2A0h+var_228], xmm0
0x18002a9d3  mov     [rbp+1A0h+var_218], r13
0x18002a9d7  mov     [rbp+1A0h+var_1D8], r14
0x18002a9db  test    r15b, 1
0x18002a9df  jnz     loc_18002AAA8
0x18002a9e5  mov     r8, r12; HSTRING
0x18002a9e8  lea     rdx, [rsp+2A0h+hMem]; this
0x18002a9ed  mov     rcx, r14; struct Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId *
0x18002a9f0  call    ?GetRealIdFromPairwiseId@@YAJAEAVStoredObjectId@TokenBroker@Authentication@Security@Internal@Windows@@0QEAUHSTRING__@@1@Z; GetRealIdFromPairwiseId(Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId &,Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId &,HSTRING__ * const,HSTRING__ * const)
0x18002a9f5  mov     ebx, eax
0x18002a9f7  cmp     eax, 80070002h
0x18002a9fc  jnz     short loc_18002AA40
0x18002a9fe  mov     rcx, [rsp+2A0h+hMem]; hMem
0x18002aa03  call    cs:__imp_LocalFree
0x18002aa09  mov     [rsp+2A0h+hMem], r13
0x18002aa0e  mov     rcx, [rsp+2A0h+var_228]; hMem
0x18002aa13  call    cs:__imp_LocalFree
0x18002aa19  mov     [rsp+2A0h+var_228], r13
0x18002aa1e  mov     rcx, [rbp+1A0h+var_228+8]; hMem
0x18002aa22  call    cs:__imp_LocalFree
0x18002aa28  mov     [rbp+1A0h+var_228+8], r13
0x18002aa2c  mov     rcx, [rbp+1A0h+var_218]; hMem
0x18002aa30  call    cs:__imp_LocalFree
0x18002aa36  mov     eax, 80070002h
0x18002aa3b  jmp     loc_18002D910
0x18002aa40  test    ebx, ebx
0x18002aa42  jns     short loc_18002AA9F
0x18002aa44  mov     rcx, [rbp+1A8h]; this
0x18002aa4b  mov     r9d, ebx; char *
0x18002aa4e  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\tokenbroker\\dat"...
0x18002aa55  mov     edx, 56Fh; void *
0x18002aa5a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002aa5f  nop
0x18002aa60  mov     rcx, [rsp+2A0h+hMem]; hMem
0x18002aa65  call    cs:__imp_LocalFree
0x18002aa6b  mov     [rsp+2A0h+hMem], r13
0x18002aa70  mov     rcx, [rsp+2A0h+var_228]; hMem
0x18002aa75  call    cs:__imp_LocalFree
0x18002aa7b  mov     [rsp+2A0h+var_228], r13
0x18002aa80  mov     rcx, [rbp+1A0h+var_228+8]; hMem
0x18002aa84  call    cs:__imp_LocalFree
0x18002aa8a  mov     [rbp+1A0h+var_228+8], r13
0x18002aa8e  mov     rcx, [rbp+1A0h+var_218]; hMem
0x18002aa92  call    cs:__imp_LocalFree
0x18002aa98  mov     eax, ebx
0x18002aa9a  jmp     loc_18002D910
0x18002aa9f  lea     rax, [rsp+2A0h+hMem]
0x18002aaa4  mov     [rbp+1A0h+var_1D8], rax
0x18002aaa8  mov     [rbp+1A0h+var_148], 5
0x18002aab0  xor     r15d, r15d
0x18002aab3  mov     [rbp+1A0h+var_140], r15d
0x18002aab7  xorps   xmm0, xmm0
0x18002aaba  movdqu  [rbp+1A0h+var_138], xmm0
0x18002aabf  mov     [rbp+1A0h+var_128], r15
0x18002aac3  lea     r8, [rbp+1A0h+var_148]; struct Windows::Internal::Security::Authentication::TokenBroker::JsonObjectReader *
0x18002aac7  mov     rdx, r12; HSTRING
0x18002aaca  lea     rcx, [rbp+1A0h+var_1D8]; struct Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId **
0x18002aace  call    ?InitializeReaderFromAccountId@@YAJAEBQEAVStoredObjectId@TokenBroker@Authentication@Security@Internal@Windows@@QEAUHSTRING__@@AEAVJsonObjectReader@23456@@Z; InitializeReaderFromAccountId(Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId * const &,HSTRING__ * const,Windows::Internal::Security::Authentication::TokenBroker::JsonObjectReader &)
0x18002aad3  mov     ebx, eax
0x18002aad5  cmp     eax, 80070002h
0x18002aada  jnz     short loc_18002AB51
0x18002aadc  mov     rcx, [rbp+1A0h+var_128]
0x18002aae0  test    rcx, rcx
0x18002aae3  jz      short loc_18002AAF2
0x18002aae5  mov     rax, [rcx]
0x18002aae8  mov     rax, [rax+10h]
0x18002aaec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002aaf1  nop
0x18002aaf2  mov     rcx, qword ptr [rbp+1A0h+var_138+8]
0x18002aaf6  test    rcx, rcx
0x18002aaf9  jz      short loc_18002AB08
0x18002aafb  mov     rax, [rcx]
0x18002aafe  mov     rax, [rax+10h]
0x18002ab02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ab07  nop
0x18002ab08  mov     rcx, qword ptr [rbp+1A0h+var_138]
0x18002ab0c  test    rcx, rcx
0x18002ab0f  jz      short loc_18002AB1E
0x18002ab11  mov     rax, [rcx]
0x18002ab14  mov     rax, [rax+10h]
0x18002ab18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ab1d  nop
0x18002ab1e  mov     rcx, [rsp+2A0h+hMem]; hMem
0x18002ab23  call    cs:__imp_LocalFree
0x18002ab29  mov     [rsp+2A0h+hMem], r15
0x18002ab2e  mov     rcx, [rsp+2A0h+var_228]; hMem
0x18002ab33  call    cs:__imp_LocalFree
0x18002ab39  mov     [rsp+2A0h+var_228], r15
0x18002ab3e  mov     rcx, [rbp+1A0h+var_228+8]; hMem
0x18002ab42  call    cs:__imp_LocalFree
0x18002ab48  mov     [rbp+1A0h+var_228+8], r15
0x18002ab4c  jmp     loc_18002AA2C
0x18002ab51  test    ebx, ebx
0x18002ab53  jns     loc_18002ABF6
0x18002ab59  mov     rcx, [rbp+1A8h]; this
0x18002ab60  mov     r9d, ebx; char *
0x18002ab63  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\tokenbroker\\dat"...
0x18002ab6a  mov     edx, 57Ah; void *
0x18002ab6f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ab74  nop
0x18002ab75  mov     rcx, [rbp+1A0h+var_128]
0x18002ab79  test    rcx, rcx
0x18002ab7c  jz      short loc_18002AB8B
0x18002ab7e  mov     rax, [rcx]
0x18002ab81  mov     rax, [rax+10h]
0x18002ab85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ab8a  nop
0x18002ab8b  mov     rcx, qword ptr [rbp+1A0h+var_138+8]
0x18002ab8f  test    rcx, rcx
0x18002ab92  jz      short loc_18002ABA1
0x18002ab94  mov     rax, [rcx]
0x18002ab97  mov     rax, [rax+10h]
0x18002ab9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002aba0  nop
0x18002aba1  mov     rcx, qword ptr [rbp+1A0h+var_138]
0x18002aba5  test    rcx, rcx
0x18002aba8  jz      short loc_18002ABB7
0x18002abaa  mov     rax, [rcx]
0x18002abad  mov     rax, [rax+10h]
0x18002abb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002abb6  nop
0x18002abb7  mov     rcx, [rsp+2A0h+hMem]; hMem
0x18002abbc  call    cs:__imp_LocalFree
0x18002abc2  mov     [rsp+2A0h+hMem], r15
0x18002abc7  mov     rcx, [rsp+2A0h+var_228]; hMem
0x18002abcc  call    cs:__imp_LocalFree
0x18002abd2  mov     [rsp+2A0h+var_228], r15
0x18002abd7  mov     rcx, [rbp+1A0h+var_228+8]; hMem
0x18002abdb  call    cs:__imp_LocalFree
0x18002abe1  mov     [rbp+1A0h+var_228+8], r15
0x18002abe5  mov     rcx, [rbp+1A0h+var_218]; hMem
0x18002abe9  call    cs:__imp_LocalFree
0x18002abef  mov     eax, ebx
0x18002abf1  jmp     loc_18002D910
0x18002abf6  mov     [rbp+1A0h+var_1F8], 5
0x18002abfd  mov     [rbp+1A0h+var_1F4], 0
0x18002ac01  xorps   xmm0, xmm0
0x18002ac04  movdqu  xmmword ptr [rbp+1A0h+string], xmm0
0x18002ac09  mov     [rbp+1A0h+var_1C0], r15
0x18002ac0d  mov     [rbp+1A0h+var_210], r15
0x18002ac11  mov     [rbp+1A0h+var_1A8], r15
0x18002ac15  mov     [rbp+1A0h+var_100], r15
0x18002ac1c  mov     [rbp+1A0h+var_F8], r15
0x18002ac23  mov     [rbp+1A0h+var_108], r15d
0x18002ac2a  mov     [rbp+1A0h+var_104], r15d
0x18002ac31  mov     rbx, r15
0x18002ac34  mov     [rbp+1A0h+var_E8], rbx
0x18002ac3b  mov     r13, r15
0x18002ac3e  mov     [rbp+1A0h+var_E0], r15
0x18002ac45  lea     r9, [rbp+1A0h+EventDescriptor]; string
0x18002ac4c  lea     r8, [rbp+1A0h+EventDescriptor.Keyword]; hstringHeader
0x18002ac53  mov     edx, 2; length
0x18002ac58  lea     rcx, aId; "Id"
0x18002ac5f  call    cs:__imp_WindowsCreateStringReference
0x18002ac65  test    eax, eax
0x18002ac67  jns     short loc_18002AC7F
0x18002ac69  xor     r9d, r9d; lpArguments
0x18002ac6c  xor     r8d, r8d; nNumberOfArguments
0x18002ac6f  mov     edx, 1; dwExceptionFlags
0x18002ac74  mov     ecx, 0C000000Dh; dwExceptionCode
0x18002ac79  call    cs:__imp_RaiseException
0x18002ac7f  lea     r8, [rbp+1A0h+var_1F8]; struct Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty *
0x18002ac83  mov     rdx, qword ptr [rbp+1A0h+EventDescriptor.Id]; HSTRING
0x18002ac8a  lea     rcx, [rbp+1A0h+var_148]; this
0x18002ac8e  call    ?GetSystemDefinedProperty@JsonObjectReader@TokenBroker@Authentication@Security@Internal@Windows@@QEAAJPEAUHSTRING__@@AEAVJsonObjectProperty@23456@@Z; Windows::Internal::Security::Authentication::TokenBroker::JsonObjectReader::GetSystemDefinedProperty(HSTRING__ *,Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty &)
0x18002ac93  mov     edi, eax
0x18002ac95  test    eax, eax
0x18002ac97  jns     short loc_18002ACE0
0x18002ac99  mov     rcx, [rbp+1A8h]; this
0x18002aca0  mov     r9d, eax; char *
0x18002aca3  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\tokenbroker\\dat"...
0x18002acaa  mov     edx, 58Bh; void *
0x18002acaf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002acb4  nop
0x18002acb5  mov     rcx, [rbp+1A0h+string+8]; string
0x18002acb9  test    rcx, rcx
0x18002acbc  jz      short loc_18002ACC5
0x18002acbe  call    cs:__imp_WindowsDeleteString
0x18002acc4  nop
0x18002acc5  mov     rcx, [rbp+1A0h+string]
0x18002acc9  test    rcx, rcx
0x18002accc  jz      short loc_18002ACDB
0x18002acce  mov     rax, [rcx]
0x18002acd1  mov     rax, [rax+10h]
  ... truncated ...
```
