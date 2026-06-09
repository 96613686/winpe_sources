# WarbirdRuntime::CEncryption<0,WarbirdCrypto::CCipherFeistel64<18,99,74,239,20,228,37,194,30,94,122,77,25,118,248,234,22,247,37,157,1,4,13,20,8,127,8,216,11,29,81,74,10,231,117,28,2,213,211,86>,WarbirdCrypto::CHashFunctionSCP<2,3,0,-2057503231663003538>,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_1,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_1>::Encrypt(WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_1 *,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_1 *)

- ea: `0x180024fd0`
- end: `0x180025060`
- name: `?Encrypt@?$CEncryption@$0A@V?$CCipherFeistel64@$0BC@$0GD@$0EK@$0OP@$0BE@$0OE@$0CF@$0MC@$0BO@$0FO@$0HK@$0EN@$0BJ@$0HG@$0PI@$0OK@$0BG@$0PH@$0CF@$0JN@$00$03$0N@$0BE@$07$0HP@$07$0NI@$0L@$0BN@$0FB@$0EK@$09$0OH@$0HF@$0BM@$01$0NF@$0ND@$0FG@@WarbirdCrypto@@V?$CHashFunctionSCP@$01$02$0A@$0?BMINLIEJLPHNNHJC@@2@UENCRYPTED_SEGMENT_DATA_CONST_1@WarbirdRuntime@@UENCRYPTED_SEGMENT_DATA_READ_WRITE_1@5@@WarbirdRuntime@@SAJPEAUENCRYPTED_SEGMENT_DATA_CONST_1@2@PEAUENCRYPTED_SEGMENT_DATA_READ_WRITE_1@2@@Z`
- size: `144`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000b900`
- `0x18001e410`

## callees

- `0x1800236a0`
- `0x180024fd0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180025038`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180025038`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180024ff1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180024ff1`

## pseudocode

```c
__int64 WarbirdRuntime::CEncryption<0,WarbirdCrypto::CCipherFeistel64<18,99,74,239,20,228,37,194,30,94,122,77,25,118,248,234,22,247,37,157,1,4,13,20,8,127,8,216,11,29,81,74,10,231,117,28,2,213,211,86>,WarbirdCrypto::CHashFunctionSCP<2,3,0,-2057503231663003538>,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_1,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_1>::Encrypt()
{
  __int64 v1; // rdx
  unsigned int v2; // ebx

  if ( !WarbirdRuntime::g_EncryptedSegmentConstData_3 )
    return 0;
  EnterCriticalSection(&WarbirdRuntime::g_encryptionLock);
  if ( WarbirdRuntime::g_EncryptedSegmentReadWriteData_3 == 1 )
  {
    v2 = WarbirdRuntime::CEncryption<0,WarbirdCrypto::CCipherFeistel64<18,99,74,239,20,228,37,194,30,94,122,77,25,118,248,234,22,247,37,157,1,4,13,20,8,127,8,216,11,29,81,74,10,231,117,28,2,213,211,86>,WarbirdCrypto::CHashFunctionSCP<2,3,0,-2057503231663003538>,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_1,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_1>::DoCrypt(
           1,
           v1,
           1);
    WarbirdRuntime::g_EncryptedSegmentReadWriteData_3 = 0;
  }
  else
  {
    v2 = 0;
    if ( (unsigned int)(WarbirdRuntime::g_EncryptedSegmentReadWriteData_3 - 1) <= 0xFFFFFFFD )
      --WarbirdRuntime::g_EncryptedSegmentReadWriteData_3;
  }
  LeaveCriticalSection(&WarbirdRuntime::g_encryptionLock);
  return v2;
}

```

## disassembly

```asm
0x180024fd0  sub     rsp, 28h
0x180024fd4  test    byte ptr cs:?g_EncryptedSegmentConstData_3@WarbirdRuntime@@3UENCRYPTED_SEGMENT_DATA_CONST_1@1@A, 1; WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_1 WarbirdRuntime::g_EncryptedSegmentConstData_3
0x180024fdb  jnz     short loc_180024FE5
0x180024fdd  xor     eax, eax
0x180024fdf  add     rsp, 28h
0x180024fe3  retn
0x180024fe5  lea     rcx, ?g_encryptionLock@WarbirdRuntime@@3VCLock@1@A; lpCriticalSection
0x180024fec  mov     [rsp+28h+var_8], rbx
0x180024ff1  call    cs:__imp_EnterCriticalSection
0x180024ff8  nop     dword ptr [rax+rax+00h]
0x180024ffd  mov     ecx, cs:?g_EncryptedSegmentReadWriteData_3@WarbirdRuntime@@3UENCRYPTED_SEGMENT_DATA_READ_WRITE_1@1@A; WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_1 WarbirdRuntime::g_EncryptedSegmentReadWriteData_3
0x180025003  cmp     ecx, 1
0x180025006  jnz     short loc_18002501E
0x180025008  mov     r8d, ecx
0x18002500b  call    ?DoCrypt@?$CEncryption@$0A@V?$CCipherFeistel64@$0BC@$0GD@$0EK@$0OP@$0BE@$0OE@$0CF@$0MC@$0BO@$0FO@$0HK@$0EN@$0BJ@$0HG@$0PI@$0OK@$0BG@$0PH@$0CF@$0JN@$00$03$0N@$0BE@$07$0HP@$07$0NI@$0L@$0BN@$0FB@$0EK@$09$0OH@$0HF@$0BM@$01$0NF@$0ND@$0FG@@WarbirdCrypto@@V?$CHashFunctionSCP@$01$02$0A@$0?BMINLIEJLPHNNHJC@@2@UENCRYPTED_SEGMENT_DATA_CONST_1@WarbirdRuntime@@UENCRYPTED_SEGMENT_DATA_READ_WRITE_1@5@@WarbirdRuntime@@CAJPEAUENCRYPTED_SEGMENT_DATA_CONST_1@2@PEAUENCRYPTED_SEGMENT_DATA_READ_WRITE_1@2@H@Z; WarbirdRuntime::CEncryption<0,WarbirdCrypto::CCipherFeistel64<18,99,74,239,20,228,37,194,30,94,122,77,25,118,248,234,22,247,37,157,1,4,13,20,8,127,8,216,11,29,81,74,10,231,117,28,2,213,211,86>,WarbirdCrypto::CHashFunctionSCP<2,3,0,-2057503231663003538>,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_1,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_1>::DoCrypt(WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_1 *,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_1 *,int)
0x180025010  mov     ebx, eax
0x180025012  mov     cs:?g_EncryptedSegmentReadWriteData_3@WarbirdRuntime@@3UENCRYPTED_SEGMENT_DATA_READ_WRITE_1@1@A, 0; WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_1 WarbirdRuntime::g_EncryptedSegmentReadWriteData_3
0x18002501c  jmp     short loc_180025031
0x18002501e  xor     ebx, ebx
0x180025020  lea     eax, [rcx-1]
0x180025023  cmp     eax, 0FFFFFFFDh
0x180025026  ja      short loc_180025031
0x180025028  lea     eax, [rcx-1]
0x18002502b  mov     cs:?g_EncryptedSegmentReadWriteData_3@WarbirdRuntime@@3UENCRYPTED_SEGMENT_DATA_READ_WRITE_1@1@A, eax; WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_1 WarbirdRuntime::g_EncryptedSegmentReadWriteData_3
0x180025031  lea     rcx, ?g_encryptionLock@WarbirdRuntime@@3VCLock@1@A; lpCriticalSection
0x180025038  call    cs:__imp_LeaveCriticalSection
0x18002503f  nop     dword ptr [rax+rax+00h]
0x180025044  mov     eax, ebx
0x180025046  mov     rbx, [rsp+28h+var_8]
0x18002504b  add     rsp, 28h
0x18002504f  retn
```
