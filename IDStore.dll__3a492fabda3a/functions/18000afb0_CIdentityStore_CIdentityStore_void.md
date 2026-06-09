# CIdentityStore::~CIdentityStore(void)

- ea: `0x18000afb0`
- end: `0x18000b097`
- name: `??1CIdentityStore@@UEAA@XZ`
- size: `231`
- prototype: `void __fastcall(CIdentityStore *this, __int64, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180010940`
- `0x180010ad0`

## callees

- `0x18000afb0`
- `0x18000b0a0`
- `0x1800191ac`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b002`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b002`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b010`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b010`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000b046`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000b046`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b02a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b02a`

## pseudocode

```c
void __fastcall CIdentityStore::~CIdentityStore(CIdentityStore *this, __int64 a2, __int64 a3)
{
  CIdentityProfileHandler *v4; // rcx
  void *v5; // rsi
  HANDLE ProcessHeap; // rax
  HKEY v7; // rcx

  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    {
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, a3, "CIdentityStore::~CIdentityStore");
      v4 = WPP_GLOBAL_Control;
    }
    if ( v4 != (CIdentityProfileHandler *)&WPP_GLOBAL_Control && (*((_DWORD *)v4 + 7) & 0x400) != 0 )
      WPP_SF_s(*((_QWORD *)v4 + 2), 12, a3, "CIdentityStore::~CIdentityStore");
  }
  CPtrArrayTemplate<CProviderInfo,AutoPtrTraits<CProviderInfo>>::RemoveAll((char *)this + 112);
  v5 = (void *)*((_QWORD *)this + 14);
  if ( v5 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v5);
    *((_QWORD *)this + 14) = 0;
    *((_QWORD *)this + 15) = 0;
  }
  v7 = (HKEY)*((_QWORD *)this + 12);
  if ( v7 != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
  {
    RegCloseKey(v7);
    *((_QWORD *)this + 12) = -1;
  }
  if ( *((_BYTE *)this + 72) )
  {
    *((_BYTE *)this + 72) = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  }
}

```

## disassembly

```asm
0x18000afb0  mov     [rsp+arg_0], rbx
0x18000afb5  mov     [rsp+arg_8], rsi
0x18000afba  push    rdi
0x18000afbb  sub     rsp, 20h
0x18000afbf  mov     rbx, rcx
0x18000afc2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000afc9  lea     rdi, WPP_GLOBAL_Control
0x18000afd0  cmp     rcx, rdi
0x18000afd3  jz      short loc_18000AFF0
0x18000afd5  test    dword ptr [rcx+1Ch], 400h
0x18000afdc  jnz     short loc_18000B05C
0x18000afde  cmp     rcx, rdi
0x18000afe1  jz      short loc_18000AFF0
0x18000afe3  test    dword ptr [rcx+1Ch], 400h
0x18000afea  jnz     loc_18000B07D
0x18000aff0  lea     rcx, [rbx+70h]
0x18000aff4  call    ?RemoveAll@?$CPtrArrayTemplate@VCProviderInfo@@U?$AutoPtrTraits@VCProviderInfo@@@@@@QEAAXXZ; CPtrArrayTemplate<CProviderInfo,AutoPtrTraits<CProviderInfo>>::RemoveAll(void)
0x18000aff9  mov     rsi, [rbx+70h]
0x18000affd  test    rsi, rsi
0x18000b000  jz      short loc_18000B020
0x18000b002  call    cs:__imp_GetProcessHeap
0x18000b008  mov     r8, rsi; lpMem
0x18000b00b  xor     edx, edx; dwFlags
0x18000b00d  mov     rcx, rax; hHeap
0x18000b010  call    cs:__imp_HeapFree
0x18000b016  xor     eax, eax
0x18000b018  mov     [rbx+70h], rax
0x18000b01c  mov     [rbx+78h], rax
0x18000b020  mov     rcx, [rbx+60h]; hKey
0x18000b024  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000b028  jz      short loc_18000B038
0x18000b02a  call    cs:__imp_RegCloseKey
0x18000b030  mov     qword ptr [rbx+60h], 0FFFFFFFFFFFFFFFFh
0x18000b038  cmp     byte ptr [rbx+48h], 0
0x18000b03c  lea     rcx, [rbx+20h]; lpCriticalSection
0x18000b040  jz      short loc_18000B04C
0x18000b042  mov     byte ptr [rcx+28h], 0
0x18000b046  call    cs:__imp_DeleteCriticalSection
0x18000b04c  mov     rbx, [rsp+28h+arg_0]
0x18000b051  mov     rsi, [rsp+28h+arg_8]
0x18000b056  add     rsp, 20h
0x18000b05a  pop     rdi
0x18000b05b  retn
0x18000b05c  mov     rcx, [rcx+10h]
0x18000b060  lea     r9, aCidentitystore_6; "CIdentityStore::~CIdentityStore"
0x18000b067  mov     edx, 0Ah
0x18000b06c  call    WPP_SF_s
0x18000b071  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b078  jmp     loc_18000AFDE
0x18000b07d  mov     rcx, [rcx+10h]
0x18000b081  lea     r9, aCidentitystore_6; "CIdentityStore::~CIdentityStore"
0x18000b088  mov     edx, 0Ch
0x18000b08d  call    WPP_SF_s
0x18000b092  jmp     loc_18000AFF0
```
