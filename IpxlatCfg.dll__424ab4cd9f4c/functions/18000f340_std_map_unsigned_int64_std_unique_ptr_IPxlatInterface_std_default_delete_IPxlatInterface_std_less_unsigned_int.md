# std::map<unsigned __int64,std::unique_ptr<IPxlatInterface,std::default_delete<IPxlatInterface>>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::unique_ptr<IPxlatInterface,std::default_delete<IPxlatInterface>>>>>::~map<unsigned __int64,std::unique_ptr<IPxlatInterface,std::default_delete<IPxlatInterface>>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::unique_ptr<IPxlatInterface,std::default_delete<IPxlatInterface>>>>>(void)

- ea: `0x18000f340`
- end: `0x18000f345`
- name: `??1?$map@_KV?$unique_ptr@VIPxlatInterface@@U?$default_delete@VIPxlatInterface@@@std@@@std@@U?$less@_K@2@V?$allocator@U?$pair@$$CB_KV?$unique_ptr@VIPxlatInterface@@U?$default_delete@VIPxlatInterface@@@std@@@std@@@std@@@2@@std@@QEAA@XZ`
- size: `5`
- prototype: `void __fastcall(void **)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800186d4`

## callees

- `0x18000f260`

## pseudocode

```c
// attributes: thunk
void __fastcall std::map<unsigned __int64,std::unique_ptr<IPxlatInterface>>::~map<unsigned __int64,std::unique_ptr<IPxlatInterface>>(
        void **a1)
{
  std::_Tree<std::_Tmap_traits<unsigned __int64,std::unique_ptr<IPxlatInterface>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::unique_ptr<IPxlatInterface>>>,0>>::~_Tree<std::_Tmap_traits<unsigned __int64,std::unique_ptr<IPxlatInterface>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::unique_ptr<IPxlatInterface>>>,0>>(a1);
}

```

## disassembly

```asm
0x18000f340  jmp     ??1?$_Tree@V?$_Tmap_traits@_KV?$unique_ptr@VIPxlatInterface@@U?$default_delete@VIPxlatInterface@@@std@@@std@@U?$less@_K@2@V?$allocator@U?$pair@$$CB_KV?$unique_ptr@VIPxlatInterface@@U?$default_delete@VIPxlatInterface@@@std@@@std@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<unsigned __int64,std::unique_ptr<IPxlatInterface>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::unique_ptr<IPxlatInterface>>>,0>>::~_Tree<std::_Tmap_traits<unsigned __int64,std::unique_ptr<IPxlatInterface>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::unique_ptr<IPxlatInterface>>>,0>>(void)
```
