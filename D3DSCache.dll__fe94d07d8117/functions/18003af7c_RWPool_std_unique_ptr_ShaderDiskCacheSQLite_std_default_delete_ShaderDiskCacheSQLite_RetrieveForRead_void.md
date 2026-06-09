# RWPool<std::unique_ptr<ShaderDiskCacheSQLite,std::default_delete<ShaderDiskCacheSQLite>>>::RetrieveForRead(void)

- ea: `0x18003af7c`
- end: `0x18003b142`
- name: `?RetrieveForRead@?$RWPool@V?$unique_ptr@VShaderDiskCacheSQLite@@U?$default_delete@VShaderDiskCacheSQLite@@@std@@@std@@@@QEAA?AVAccessor@1@XZ`
- size: `454`
- prototype: `_QWORD *__fastcall(__int64, __int64)`
- caller_count: `5`
- callee_count: `10`
- tags: ``

## callers

- `0x18003a5d8`
- `0x180047480`
- `0x1800474f0`
- `0x180047570`
- `0x1800506d8`

## callees

- `0x18003af7c`
- `0x18003b148`
- `0x18003b170`
- `0x18003b220`
- `0x18003e9f0`
- `0x180042394`
- `0x1800445c4`
- `0x18004fd80`
- `0x18004ff18`
- `0x1800502f0`

## import_xrefs

- `msvcp_win!_Cnd_wait` at `0x18003afe7`
- `msvcp_win!_Cnd_wait` at `0x18003afe7`

## pseudocode

```c
_QWORD *__fastcall RWPool<std::unique_ptr<ShaderDiskCacheSQLite>>::RetrieveForRead(__int64 a1, __int64 a2)
{
  __int64 v4; // rdx
  __int64 v5; // rcx
  unsigned __int64 v6; // rax
  __int64 *v7; // rax
  __int64 v8; // rax
  __int64 v9; // rax
  _QWORD *result; // rax
  __int64 v11; // rbx
  __int64 v12; // rax
  __int64 v13; // rax
  _QWORD *v14; // rcx
  __int64 v15; // rax
  __int64 v16; // [rsp+28h] [rbp-70h] BYREF
  char v17; // [rsp+30h] [rbp-68h]
  _Mtx_t v18; // [rsp+38h] [rbp-60h] BYREF
  char v19; // [rsp+40h] [rbp-58h]
  ShaderDiskCacheSQLite *v20; // [rsp+48h] [rbp-50h] BYREF
  __int64 v21; // [rsp+50h] [rbp-48h]
  __int64 v22; // [rsp+58h] [rbp-40h]
  char v23; // [rsp+60h] [rbp-38h]
  __int64 v24; // [rsp+68h] [rbp-30h]
  char v25; // [rsp+70h] [rbp-28h]
  __int64 v26; // [rsp+A0h] [rbp+8h] BYREF
  _QWORD *v27; // [rsp+A8h] [rbp+10h]
  unsigned __int64 v28; // [rsp+B0h] [rbp+18h] BYREF

  v27 = (_QWORD *)a2;
  v26 = a1;
  v16 = a1 + 24;
  v17 = 1;
  Smtx_lock_shared((_Smtx_t *)(a1 + 24));
  v18 = (_Mtx_t)(a1 + 32);
  std::_Mutex_base::lock((std::_Mutex_base *)(a1 + 32));
  v19 = 1;
  while ( 1 )
  {
    v4 = *(_QWORD *)a1;
    v5 = *(_QWORD *)(a1 + 8);
    if ( *(_QWORD *)a1 != v5 )
    {
      v8 = *(_QWORD *)(v5 - 8);
      *(_QWORD *)(v5 - 8) = 0;
      v26 = v8;
      RWPool<std::unique_ptr<ShaderDiskCacheSQLite>>::Accessor::Accessor((__int64)&v20, a1, &v26, (__int64)&v16);
      std::vector<std::unique_ptr<ShaderDiskCacheSQLite>>::pop_back(a1);
      *(_QWORD *)a2 = v20;
      v9 = v21;
      v21 = 0;
      *(_QWORD *)(a2 + 8) = v9;
      *(_QWORD *)(a2 + 16) = v22;
      *(_BYTE *)(a2 + 24) = v23;
      v22 = 0;
      v23 = 0;
      *(_QWORD *)(a2 + 32) = v24;
      *(_BYTE *)(a2 + 40) = v25;
      v24 = 0;
      v25 = 0;
      RWPool<std::unique_ptr<ShaderDiskCacheSQLite>>::Accessor::~Accessor(&v20);
      std::unique_lock<std::mutex>::~unique_lock<std::mutex>(&v18);
      std::shared_lock<std::shared_mutex>::~shared_lock<std::shared_mutex>(&v16);
      return (_QWORD *)a2;
    }
    if ( *(_DWORD *)(a1 + 176) < *(_DWORD *)(a1 + 180) )
      break;
    _Cnd_wait((_Cnd_t)(a1 + 184), (_Mtx_t)(a1 + 32));
  }
  v28 = (unsigned int)++*(_DWORD *)(a1 + 176);
  v6 = (*(_QWORD *)(a1 + 16) - v4) >> 3;
  if ( v28 > v6 )
    std::vector<std::unique_ptr<ShaderDiskCacheSQLite>>::_Reallocate<0>((_QWORD *)a1, &v28);
  try
  {
    v7 = (__int64 *)std::_Func_class<std::unique_ptr<ShaderDiskCacheSQLite>,>::operator()(a1 + 112, (__int64)&v28);
    RWPool<std::unique_ptr<ShaderDiskCacheSQLite>>::Accessor::Accessor(a2, a1, v7, (__int64)&v16);
    std::unique_lock<std::mutex>::~unique_lock<std::mutex>(&v18);
    std::shared_lock<std::shared_mutex>::~shared_lock<std::shared_mutex>(&v16);
    result = (_QWORD *)a2;
  }
  catch ( ... )
  {
    v11 = v26;
    --*(_DWORD *)(v26 + 176);
    while ( 1 )
    {
      v12 = *(_QWORD *)(v11 + 8);
      if ( *(_QWORD *)v11 != v12 )
        break;
      _Cnd_wait((_Cnd_t)(v11 + 184), v18);
    }
    v13 = *(_QWORD *)(v12 - 8);
    *(_QWORD *)(*(_QWORD *)(v11 + 8) - 8LL) = 0;
    v26 = v13;
    RWPool<std::unique_ptr<ShaderDiskCacheSQLite>>::Accessor::Accessor((__int64)&v20, v11, &v26, (__int64)&v16);
    std::vector<std::unique_ptr<ShaderDiskCacheSQLite>>::pop_back(v11);
    v14 = v27;
    *v27 = v20;
    v15 = v21;
    v21 = 0;
    v14[1] = v15;
    v14[2] = v22;
    *((_BYTE *)v14 + 24) = v23;
    v22 = 0;
    v23 = 0;
    v14[4] = v24;
    *((_BYTE *)v14 + 40) = v25;
    v24 = 0;
    v25 = 0;
    RWPool<std::unique_ptr<ShaderDiskCacheSQLite>>::Accessor::~Accessor(&v20);
    std::unique_lock<std::mutex>::~unique_lock<std::mutex>(&v18);
    std::shared_lock<std::shared_mutex>::~shared_lock<std::shared_mutex>(&v16);
    return v27;
  }
  return result;
}

```

## disassembly

```asm
0x18003af7c  mov     rax, rsp
0x18003af7f  mov     [rax+10h], rdx
0x18003af83  mov     [rax+8], rcx
0x18003af87  push    rbx
0x18003af88  push    rsi
0x18003af89  push    rdi
0x18003af8a  sub     rsp, 80h
0x18003af91  mov     rdi, rdx
0x18003af94  mov     rbx, rcx
0x18003af97  add     rcx, 18h; _Smtx_t *
0x18003af9b  mov     [rax-70h], rcx
0x18003af9f  mov     byte ptr [rax-68h], 1
0x18003afa3  call    _Smtx_lock_shared
0x18003afa8  nop
0x18003afa9  lea     rsi, [rbx+20h]
0x18003afad  mov     [rsp+98h+var_60], rsi
0x18003afb2  mov     rcx, rsi; this
0x18003afb5  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x18003afba  mov     [rsp+98h+var_58], 1
0x18003afbf  mov     rdx, [rbx]
0x18003afc2  mov     rcx, [rbx+8]
0x18003afc6  cmp     rdx, rcx
0x18003afc9  jnz     loc_18003B088
0x18003afcf  mov     eax, [rbx+0B4h]
0x18003afd5  cmp     [rbx+0B0h], eax
0x18003afdb  jb      short loc_18003AFEF
0x18003afdd  lea     rcx, [rbx+0B8h]; _Cnd_t
0x18003afe4  mov     rdx, rsi; _Mtx_t
0x18003afe7  call    cs:__imp__Cnd_wait
0x18003afed  jmp     short loc_18003AFBF
0x18003afef  inc     dword ptr [rbx+0B0h]
0x18003aff5  mov     ecx, [rbx+0B0h]
0x18003affb  mov     [rsp+98h+arg_10], rcx
0x18003b003  mov     rax, [rbx+10h]
0x18003b007  sub     rax, rdx
0x18003b00a  sar     rax, 3
0x18003b00e  cmp     rcx, rax
0x18003b011  jbe     short loc_18003B024
0x18003b013  lea     rdx, [rsp+98h+arg_10]
0x18003b01b  mov     rcx, rbx
0x18003b01e  call    ??$_Reallocate@$0A@@?$vector@V?$unique_ptr@VShaderDiskCacheSQLite@@U?$default_delete@VShaderDiskCacheSQLite@@@std@@@std@@V?$allocator@V?$unique_ptr@VShaderDiskCacheSQLite@@U?$default_delete@VShaderDiskCacheSQLite@@@std@@@std@@@2@@std@@AEAAXAEA_K@Z; std::vector<std::unique_ptr<ShaderDiskCacheSQLite>>::_Reallocate<0>(unsigned __int64 &)
0x18003b023  nop
0x18003b024  lea     rcx, [rbx+70h]
0x18003b028  lea     rdx, [rsp+98h+arg_10]
0x18003b030  call    ??R?$_Func_class@V?$unique_ptr@VShaderDiskCacheSQLite@@U?$default_delete@VShaderDiskCacheSQLite@@@std@@@std@@$$V@std@@QEBA?AV?$unique_ptr@VShaderDiskCacheSQLite@@U?$default_delete@VShaderDiskCacheSQLite@@@std@@@1@XZ; std::_Func_class<std::unique_ptr<ShaderDiskCacheSQLite>,>::operator()(void)
0x18003b035  lea     r9, [rsp+98h+var_70]
0x18003b03a  mov     r8, rax
0x18003b03d  mov     rdx, rbx
0x18003b040  mov     rcx, rdi
0x18003b043  call    ??0Accessor@?$RWPool@V?$unique_ptr@VShaderDiskCacheSQLite@@U?$default_delete@VShaderDiskCacheSQLite@@@std@@@std@@@@QEAA@AEAV1@V?$unique_ptr@VShaderDiskCacheSQLite@@U?$default_delete@VShaderDiskCacheSQLite@@@std@@@std@@AEAV?$shared_lock@Vshared_mutex@std@@@3@@Z; RWPool<std::unique_ptr<ShaderDiskCacheSQLite>>::Accessor::Accessor(RWPool<std::unique_ptr<ShaderDiskCacheSQLite>> &,std::unique_ptr<ShaderDiskCacheSQLite>,std::shared_lock<std::shared_mutex> &)
0x18003b048  nop
0x18003b049  lea     rcx, [rsp+98h+var_60]
0x18003b04e  call    ??1?$unique_lock@Vmutex@std@@@std@@QEAA@XZ; std::unique_lock<std::mutex>::~unique_lock<std::mutex>(void)
0x18003b053  nop
0x18003b054  lea     rcx, [rsp+98h+var_70]
0x18003b059  call    ??1?$shared_lock@Vshared_mutex@std@@@std@@QEAA@XZ; std::shared_lock<std::shared_mutex>::~shared_lock<std::shared_mutex>(void)
0x18003b05e  mov     rax, rdi
0x18003b061  jmp     loc_18003B137
0x18003b066  lea     rcx, [rsp+98h+var_60]
0x18003b06b  call    ??1?$unique_lock@Vmutex@std@@@std@@QEAA@XZ; std::unique_lock<std::mutex>::~unique_lock<std::mutex>(void)
0x18003b070  nop
0x18003b071  lea     rcx, [rsp+98h+var_70]
0x18003b076  call    ??1?$shared_lock@Vshared_mutex@std@@@std@@QEAA@XZ; std::shared_lock<std::shared_mutex>::~shared_lock<std::shared_mutex>(void)
0x18003b07b  mov     rax, [rsp+98h+arg_8]
0x18003b083  jmp     loc_18003B137
0x18003b088  mov     rax, [rcx-8]
0x18003b08c  mov     qword ptr [rcx-8], 0
0x18003b094  mov     [rsp+98h+arg_0], rax
0x18003b09c  lea     r9, [rsp+98h+var_70]
0x18003b0a1  lea     r8, [rsp+98h+arg_0]
0x18003b0a9  mov     rdx, rbx
0x18003b0ac  lea     rcx, [rsp+98h+var_50]
0x18003b0b1  call    ??0Accessor@?$RWPool@V?$unique_ptr@VShaderDiskCacheSQLite@@U?$default_delete@VShaderDiskCacheSQLite@@@std@@@std@@@@QEAA@AEAV1@V?$unique_ptr@VShaderDiskCacheSQLite@@U?$default_delete@VShaderDiskCacheSQLite@@@std@@@std@@AEAV?$shared_lock@Vshared_mutex@std@@@3@@Z; RWPool<std::unique_ptr<ShaderDiskCacheSQLite>>::Accessor::Accessor(RWPool<std::unique_ptr<ShaderDiskCacheSQLite>> &,std::unique_ptr<ShaderDiskCacheSQLite>,std::shared_lock<std::shared_mutex> &)
0x18003b0b6  mov     rcx, rbx
0x18003b0b9  call    ?pop_back@?$vector@V?$unique_ptr@VShaderDiskCacheSQLite@@U?$default_delete@VShaderDiskCacheSQLite@@@std@@@std@@V?$allocator@V?$unique_ptr@VShaderDiskCacheSQLite@@U?$default_delete@VShaderDiskCacheSQLite@@@std@@@std@@@2@@std@@QEAAXXZ; std::vector<std::unique_ptr<ShaderDiskCacheSQLite>>::pop_back(void)
0x18003b0be  mov     rax, [rsp+98h+var_50]
0x18003b0c3  mov     [rdi], rax
0x18003b0c6  mov     rax, [rsp+98h+var_48]
0x18003b0cb  mov     [rsp+98h+var_48], 0
0x18003b0d4  mov     [rdi+8], rax
0x18003b0d8  mov     rax, [rsp+98h+var_40]
0x18003b0dd  mov     [rdi+10h], rax
0x18003b0e1  mov     al, [rsp+98h+var_38]
0x18003b0e5  mov     [rdi+18h], al
0x18003b0e8  mov     [rsp+98h+var_40], 0
0x18003b0f1  mov     [rsp+98h+var_38], 0
0x18003b0f6  mov     rax, [rsp+98h+var_30]
0x18003b0fb  mov     [rdi+20h], rax
0x18003b0ff  mov     al, [rsp+98h+var_28]
0x18003b103  mov     [rdi+28h], al
0x18003b106  mov     [rsp+98h+var_30], 0
0x18003b10f  mov     [rsp+98h+var_28], 0
0x18003b114  lea     rcx, [rsp+98h+var_50]
0x18003b119  call    ??1Accessor@?$RWPool@V?$unique_ptr@VShaderDiskCacheSQLite@@U?$default_delete@VShaderDiskCacheSQLite@@@std@@@std@@@@QEAA@XZ; RWPool<std::unique_ptr<ShaderDiskCacheSQLite>>::Accessor::~Accessor(void)
0x18003b11e  nop
0x18003b11f  lea     rcx, [rsp+98h+var_60]
0x18003b124  call    ??1?$unique_lock@Vmutex@std@@@std@@QEAA@XZ; std::unique_lock<std::mutex>::~unique_lock<std::mutex>(void)
0x18003b129  nop
0x18003b12a  lea     rcx, [rsp+98h+var_70]
0x18003b12f  call    ??1?$shared_lock@Vshared_mutex@std@@@std@@QEAA@XZ; std::shared_lock<std::shared_mutex>::~shared_lock<std::shared_mutex>(void)
0x18003b134  mov     rax, rdi
0x18003b137  add     rsp, 80h
0x18003b13e  pop     rdi
0x18003b13f  pop     rsi
0x18003b140  pop     rbx
0x18003b141  retn
```
