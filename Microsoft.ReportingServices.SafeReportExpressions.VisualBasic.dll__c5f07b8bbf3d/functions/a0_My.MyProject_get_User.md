# My.MyProject::get_User

- ea: `0xa0`
- end: `0xab`
- name: `My.MyProject::get_User`
- size: `11`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c

```

## disassembly

```asm
0xa0  ldsfld   class ThreadSafeObjectProvider`1<class [Microsoft.VisualBasic]Microsoft.VisualBasic.ApplicationServices.User> My.MyProject::m_UserObjectProvider
0xa5  callvirt instance var<u1> class ThreadSafeObjectProvider`1<class [Microsoft.VisualBasic]Microsoft.VisualBasic.ApplicationServices.User>::get_GetInstance()
0xaa  ret
```
