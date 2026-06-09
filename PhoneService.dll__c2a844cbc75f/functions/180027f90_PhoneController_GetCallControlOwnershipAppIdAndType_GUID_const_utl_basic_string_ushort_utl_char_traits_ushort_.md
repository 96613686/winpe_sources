# PhoneController::GetCallControlOwnershipAppIdAndType(_GUID const &,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *,PhoneOwningAppType *,ISecurityToken *)

- ea: `0x180027f90`
- end: `0x1800281c8`
- name: `?GetCallControlOwnershipAppIdAndType@PhoneController@@UEAAJAEBU_GUID@@PEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@PEAW4PhoneOwningAppType@@PEAUISecurityToken@@@Z`
- size: `568`
- prototype: `__int64 __usercall@<rax>(PhoneController *this@<rcx>, struct _GUID *@<rdx>, struct ISecurityToken *)`
- caller_count: `0`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callees

- `0x180006e94`
- `0x18001de50`
- `0x18001f514`
- `0x180027f90`
- `0x18002c580`
- `0x18003617c`
- `0x180051e44`
- `0x180070030`
- `0x180071ba8`
- `0x18008d95a`
- `0x18008d9b0`
- `0x18008f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002808e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002808e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180028136`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180028183`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180028136`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180028183`

## string_xrefs

- `0x180028006`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x18002804f`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x180028149`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x1800280bc`: `onecoreuap\net\phone\phoneservice\service\lib\phoneline.cpp`
- `0x18002810c`: `onecoreuap\net\phone\phoneservice\service\lib\phoneline.cpp`

## pseudocode

```c

```
