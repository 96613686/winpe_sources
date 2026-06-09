# RWPool<std::unique_ptr<ShaderDiskCacheSQLite,std::default_delete<ShaderDiskCacheSQLite>>>::Accessor::~Accessor(void)

- ea: `0x18003b170`
- end: `0x18003b218`
- name: `??1Accessor@?$RWPool@V?$unique_ptr@VShaderDiskCacheSQLite@@U?$default_delete@VShaderDiskCacheSQLite@@@std@@@std@@@@QEAA@XZ`
- size: `168`
- prototype: `void __fastcall(ShaderDiskCacheSQLite **)`
- caller_count: `25`
- callee_count: `7`
- tags: ``

## callers

- `0x18002a2d0`
- `0x18003a5d8`
- `0x18003af7c`
- `0x180042f8c`
- `0x1800473a0`
- `0x180047410`
- `0x180047480`
- `0x1800474f0`
- `0x180047570`
- `0x180047960`
- `0x180050324`
- `0x180050438`
- `0x180050574`
- `0x18005063c`
- `0x1800506d8`
- `0x180050a28`
- `0x180050c98`
- `0x1800a7011`
- `0x1800a7047`
- `0x1800a727f`
- `0x1800a768c`
- `0x1800a769e`
- `0x1800a76c2`
- `0x1800a76f8`
- `0x1800a770a`

## callees

- `0x18003b170`
- `0x18003b220`
- `0x18003b240`
- `0x18003b270`
- `0x18003e9f0`
- `0x180041a38`
- `0x18004fc50`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x18003b1d5`
- `msvcp_win!_Mtx_unlock` at `0x18003b1d5`
- `msvcp_win!_Cnd_signal` at `0x18003b1e5`
- `msvcp_win!_Cnd_signal` at `0x18003b1e5`

## pseudocode

```c
void __fastcall RWPool<std::unique_ptr<ShaderDiskCacheSQLite>>::Accessor::~Accessor(ShaderDiskCacheSQLite **a1)
{
  ShaderDiskCacheSQLite *v2; // rcx
  ShaderDiskCacheSQLite **v3; // rsi
  ShaderDiskCacheSQLite **v4; // rdx
  ShaderDiskCacheSQLite *v5; // rax
  ShaderDiskCacheSQLite *v6; // rbx

  if ( *((_BYTE *)a1 + 24) )
  {
    v2 = *a1;
    v3 = a1 + 1;
    v4 = (ShaderDiskCacheSQLite **)*((_QWORD *)v2 + 1);
    if ( v4 == *((ShaderDiskCacheSQLite ***)v2 + 2) )
    {
      std::vector<std::unique_ptr<ShaderDiskCacheSQLite>>::_Emplace_reallocate<std::unique_ptr<ShaderDiskCacheSQLite>>(
        v2,
        (__int64)v4,
        (__int64 *)a1 + 1);
    }
    else
    {
      v5 = *v3;
      *v3 = 0;
      *v4 = v5;
      *((_QWORD *)v2 + 1) += 8LL;
    }
  }
  else if ( *((_BYTE *)a1 + 40) )
  {
    v6 = *a1;
    std::_Mutex_base::lock((ShaderDiskCacheSQLite *)((char *)*a1 + 32));
    v3 = a1 + 1;
    std::vector<std::unique_ptr<ShaderDiskCacheSQLite>>::push_back(*a1, a1 + 1);
    _Mtx_unlock((ShaderDiskCacheSQLite *)((char *)v6 + 32));
    _Cnd_signal((ShaderDiskCacheSQLite *)((char *)*a1 + 184));
  }
  else
  {
    v3 = a1 + 1;
  }
  std::shared_lock<std::shared_mutex>::~shared_lock<std::shared_mutex>(a1 + 4);
  std::unique_lock<std::shared_mutex>::~unique_lock<std::shared_mutex>(a1 + 2);
  std::unique_ptr<ShaderDiskCacheSQLite>::~unique_ptr<ShaderDiskCacheSQLite>(v3);
}

```

## disassembly

```asm
0x18003b170  push    rbx
0x18003b172  push    rbp
0x18003b173  push    rsi
0x18003b174  push    rdi
0x18003b175  sub     rsp, 28h
0x18003b179  mov     rdi, rcx
0x18003b17c  xor     r8d, r8d
0x18003b17f  cmp     [rcx+18h], r8b
0x18003b183  jz      short loc_18003B1B0
0x18003b185  mov     rcx, [rcx]
0x18003b188  lea     rsi, [rdi+8]
0x18003b18c  mov     rdx, [rcx+8]
0x18003b190  cmp     rdx, [rcx+10h]
0x18003b194  jz      short loc_18003B1A6
0x18003b196  mov     rax, [rsi]
0x18003b199  mov     [rsi], r8
0x18003b19c  mov     [rdx], rax
0x18003b19f  add     qword ptr [rcx+8], 8
0x18003b1a4  jmp     short loc_18003B1F1
0x18003b1a6  mov     r8, rsi
0x18003b1a9  call    ??$_Emplace_reallocate@V?$unique_ptr@VShaderDiskCacheSQLite@@U?$default_delete@VShaderDiskCacheSQLite@@@std@@@std@@@?$vector@V?$unique_ptr@VShaderDiskCacheSQLite@@U?$default_delete@VShaderDiskCacheSQLite@@@std@@@std@@V?$allocator@V?$unique_ptr@VShaderDiskCacheSQLite@@U?$default_delete@VShaderDiskCacheSQLite@@@std@@@std@@@2@@std@@AEAAPEAV?$unique_ptr@VShaderDiskCacheSQLite@@U?$default_delete@VShaderDiskCacheSQLite@@@std@@@1@QEAV21@$$QEAV21@@Z; std::vector<std::unique_ptr<ShaderDiskCacheSQLite>>::_Emplace_reallocate<std::unique_ptr<ShaderDiskCacheSQLite>>(std::unique_ptr<ShaderDiskCacheSQLite> * const,std::unique_ptr<ShaderDiskCacheSQLite> &&)
0x18003b1ae  jmp     short loc_18003B1F1
0x18003b1b0  cmp     [rcx+28h], r8b
0x18003b1b4  jz      short loc_18003B1ED
0x18003b1b6  mov     rbx, [rcx]
0x18003b1b9  lea     rcx, [rbx+20h]; this
0x18003b1bd  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x18003b1c2  lea     rsi, [rdi+8]
0x18003b1c6  mov     rdx, rsi
0x18003b1c9  mov     rcx, [rdi]
0x18003b1cc  call    ?push_back@?$vector@V?$unique_ptr@VShaderDiskCacheSQLite@@U?$default_delete@VShaderDiskCacheSQLite@@@std@@@std@@V?$allocator@V?$unique_ptr@VShaderDiskCacheSQLite@@U?$default_delete@VShaderDiskCacheSQLite@@@std@@@std@@@2@@std@@QEAAX$$QEAV?$unique_ptr@VShaderDiskCacheSQLite@@U?$default_delete@VShaderDiskCacheSQLite@@@std@@@2@@Z; std::vector<std::unique_ptr<ShaderDiskCacheSQLite>>::push_back(std::unique_ptr<ShaderDiskCacheSQLite> &&)
0x18003b1d1  lea     rcx, [rbx+20h]; _Mtx_t
0x18003b1d5  call    cs:__imp__Mtx_unlock
0x18003b1db  mov     rcx, [rdi]
0x18003b1de  add     rcx, 0B8h; _Cnd_t
0x18003b1e5  call    cs:__imp__Cnd_signal
0x18003b1eb  jmp     short loc_18003B1F1
0x18003b1ed  lea     rsi, [rcx+8]
0x18003b1f1  mov     eax, 20h ; ' '
0x18003b1f6  lea     rcx, [rdi+rax]
0x18003b1fa  call    ??1?$shared_lock@Vshared_mutex@std@@@std@@QEAA@XZ; std::shared_lock<std::shared_mutex>::~shared_lock<std::shared_mutex>(void)
0x18003b1ff  lea     rcx, [rdi+10h]
0x18003b203  call    ??1?$unique_lock@Vshared_mutex@std@@@std@@QEAA@XZ; std::unique_lock<std::shared_mutex>::~unique_lock<std::shared_mutex>(void)
0x18003b208  mov     rcx, rsi
0x18003b20b  add     rsp, 28h
0x18003b20f  pop     rdi
0x18003b210  pop     rsi
0x18003b211  pop     rbp
0x18003b212  pop     rbx
0x18003b213  jmp     ??1?$unique_ptr@VShaderDiskCacheSQLite@@U?$default_delete@VShaderDiskCacheSQLite@@@std@@@std@@QEAA@XZ; std::unique_ptr<ShaderDiskCacheSQLite>::~unique_ptr<ShaderDiskCacheSQLite>(void)
```
