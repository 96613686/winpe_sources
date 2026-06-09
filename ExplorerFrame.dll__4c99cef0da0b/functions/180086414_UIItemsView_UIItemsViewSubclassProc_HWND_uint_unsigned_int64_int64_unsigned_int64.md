# UIItemsView::_UIItemsViewSubclassProc(HWND__ *,uint,unsigned __int64,__int64,unsigned __int64)

- ea: `0x180086414`
- end: `0x1800867a4`
- name: `?_UIItemsViewSubclassProc@UIItemsView@@QEAA_JPEAUHWND__@@I_K_J1@Z`
- size: `912`
- prototype: `__int64 __usercall@<rax>(UIItemsView *__hidden this@<rcx>, HWND hWnd@<rdx>, unsigned int@<r8d>, unsigned __int64@<r9>, __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800863e0`

## callees

- `0x180047410`
- `0x180086414`
- `0x1800867b0`
- `0x1800872a4`
- `0x1800da098`
- `0x18013f7d0`
- `0x1801406ec`
- `0x1801e4e9c`
- `0x180210010`

## import_xrefs

- `SHCORE!IUnknown_QueryService` at `0x18008657b`
- `SHCORE!IUnknown_QueryService` at `0x18008657b`
- `USER32!EndPaint` at `0x180086555`
- `USER32!EndPaint` at `0x180086722`
- `USER32!EndPaint` at `0x180086555`
- `USER32!EndPaint` at `0x180086722`
- `USER32!BeginPaint` at `0x18008652c`
- `USER32!BeginPaint` at `0x1800866bb`
- `USER32!BeginPaint` at `0x18008652c`
- `USER32!BeginPaint` at `0x1800866bb`
- `USER32!SendMessageW` at `0x180086619`
- `USER32!SendMessageW` at `0x1800866fc`
- `USER32!SendMessageW` at `0x180086619`
- `USER32!SendMessageW` at `0x1800866fc`
- `USER32!GetKeyState` at `0x180086638`
- `USER32!GetKeyState` at `0x180086638`
- `USER32!GetAncestor` at `0x180086604`
- `USER32!GetAncestor` at `0x180086604`
- `USER32!PostMessageW` at `0x180086799`
- `USER32!PostMessageW` at `0x180086799`
- `UxTheme!BeginBufferedPaint` at `0x1800866dc`
- `UxTheme!BeginBufferedPaint` at `0x1800866dc`
- `UxTheme!EndBufferedPaint` at `0x180086715`
- `UxTheme!EndBufferedPaint` at `0x180086715`
- `UxTheme!IsCompositionActive` at `0x1800864e4`
- `UxTheme!IsCompositionActive` at `0x1800864e4`
- `UxTheme!BufferedPaintSetAlpha` at `0x18008670a`
- `UxTheme!BufferedPaintSetAlpha` at `0x18008670a`
- `UxTheme!BufferedPaintUnInit` at `0x180086665`
- `UxTheme!BufferedPaintUnInit` at `0x180086665`

## pseudocode

```c

```
