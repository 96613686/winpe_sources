# My.MyProject::get_WebServices

- ea: `0xb0`
- end: `0xbb`
- name: `My.MyProject::get_WebServices`
- size: `11`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task`

## pseudocode

```c

```

## disassembly

```asm
0xb0  ldsfld   class ThreadSafeObjectProvider`1<class MyWebServices> My.MyProject::m_MyWebServicesObjectProvider
0xb5  callvirt instance var<u1> class ThreadSafeObjectProvider`1<class MyWebServices>::get_GetInstance()
0xba  ret
```
